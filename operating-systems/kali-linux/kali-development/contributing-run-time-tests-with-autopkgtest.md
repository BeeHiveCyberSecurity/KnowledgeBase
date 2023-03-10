# Contributing run-time tests with autopkgtest

[Why Kali could benefit from your help](broken-reference)

With Kali Linux being a rolling distribution it will occasionally have packages that break due to changes in their dependencies. To best combat this, we have set up [automated runtime tests](https://autopkgtest.kali.org/) that have to be passed in order to allow the packages to migrate into [kali-rolling](https://www.kali.org/docs/general-use/kali-branches/). However, most packages at this time don’t have a comprehensive autopkgtest associated with it causing this process to not reach its full potential. This is where the community can help us, by contributing test for packages that lack them.

[A bit of autopkgtest background](broken-reference)

Autopkgtests were created as a way to test a package as accurately as possible on a real Debian system. This method can leverage virtualization and containers to create an accurate and re-usable environment that will be the testing area. There is a lot more information available on this topic. For a more in depth look than what will be covered here please see the following articles (which served as sources of information during writing):

* [The official Debian CI doc page](https://ci.debian.net/doc/file.TUTORIAL.html)
* [A great talk covering autopkgtests](http://meetings-archive.debian.net/pub/debian-meetings/2015/debconf15/Tutorial\_functional\_testing\_of\_Debian\_packages.webm)
* [A paper going in-depth on writing As-Installed tests](https://gitlab.com/terceiro/installed-tests-patterns/raw/pdf/final/installed-tests-patterns.pdf)
* [The best practices Debian wiki page](https://wiki.debian.org/ContinuousIntegration/AutopkgtestBestPractices)

We encourage users to spend some time looking through these after finishing reading the rest of this doc. We will only be really covering a small portion of what is a large topic to explore and learn.

[Structuring Test Files](broken-reference)

Adding autopkgtests to a source package is a matter of creating a `debian/tests/control` file: that file describes all the tests that have to be run. Just like `debian/control`, it uses a set of entries structured like mail headers (e.g. `Field-Name: some value`). In the simplest case, the test can be fully described in the control file, but for most non-trivial tests, you will just reference an external test script that you will just put alongside in `debian/tests/`.

Have a look a the [official documentation of those control files](https://salsa.debian.org/ci-team/autopkgtest/-/blob/master/doc/README.package-tests.rst) to gain a good idea of what we are doing and what’s possible. A lot of the options are explained quite well, and through active experimentation and learning can be utilized in helpful ways, but for now we will stick to some of the basics. Lets take a look at their example control file:

```
Tests: fred, bill, bongo
Depends: pkg1, pkg2 [amd64] | pkg3 (>= 3)
Restrictions: needs-root, breaks-testbed
```

We can break this down pretty quickly. There are three test scripts: fred, bill, and bongo. These three test scripts exist in `debian/tests/`. While we don’t know what these tests do, we do know through the `Depends` fields that they will require two packages (the example voluntarily shows some advanced dependency syntax that you will usually not need, but for the sake of the explanation it means that you always want `pkg1`, and on an amd64 machine, you also need `pkg2`, while on other machines, you will want `pkg3` with a version greater or equalt to 3). We also know that this test suite needs to use the root user, or have elevated privileges, and also has the potential to break the testbed (which means that autopkgtest will refuse to run the test if the testbed can’t be easily restored).

Looking at another example that they have:

```
Test-Command: foo-cli --list --verbose
Depends: foo
Restrictions: needs-root
```

Here we see that they are running a test through `Test-Command`. This is a way to prevent creating scripts to run tests, and can come in handy to prevent having a one-liner script that is being called. In this case, they run `foo-cli` which we can tell is part of the `foo` package, as shown by the Depends field. It seems like this test is superficial, as it is only one line, which should be noted in the Restrictions, so if this was a real package we may have wanted to investigate further. We can most commonly tell if a test should contain `Restrictions: superficial` if they only use one line of commands to test the tool.

Control files will include one of the methods of testing, whether it is a script or a one-liner, what the test depends on, and any potential restrictions or problems that the test might have. Keep in mind that if your test only needs the built binary packages, then you don’t need to specify any explicit `Depends` field as you can rely on the default value of `Depends: @`.

If you want to install a supplementary package `foobar` for your test, then you would use `Depends: @, foobar` as `@` is as shorthand for the binary packages generated by the source package containing the tests.

A few other important restrictions that should be remembered (but do look through all that are possible!):

* `allow-stderr` - Accepts output to `stderr` and will not fail when there it receives any.
* `rw-build-tree` - The test will have access to the built source tree, with certain conditions applied.
* `isolation-container` - Any services or open TCP ports that are a part of the test will utilize their own container or VM to prevent fails.
* `isolation-machine` - The test will likely interact with the container/VM in a way that would typically result in an error, such as rebooting or interacting with the kernel.
* `needs-internet` - The test will need unrestricted access to the internet.

[Learning by examples](broken-reference)

There are a few things to learn about with autopkgtests that we can see in action already. We will look at what tests can look like, what types are more beneficial, and a few tricks that we can see.

The [cloud\_enum](https://gitlab.com/kalilinux/packages/cloud-enum/-/tree/kali/master/debian/tests) control file looks like the following:

cloud\_enum control file

```
Test-Command: cloud_enum --help
Depends: @
Restrictions: superficial
```

Whereas the [python-pip](https://gitlab.com/kalilinux/packages/python-pip/-/tree/kali/master/debian/tests) control file looks like the following:

python-pip control file

```
Tests: pip3-root.sh
Restrictions: needs-root

Tests: pip3-user.sh
Restrictions: breaks-testbed

# https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=823358
Tests: pip3-editable.sh
```

With includes a test that looks like:

python-pip pip3-user.sh test file

```
#!/bin/sh

export HOME=$AUTOPKGTEST_TMP
export PATH=$PATH:$HOME/.local/bin
export PIP_DISABLE_PIP_VERSION_CHECK=1

if [ $(id -u) = 0 ]
then
    adduser --quiet --system --group --no-create-home testing
    user=testing
    mkdir $HOME/.cache
    chown -R $user $HOME
    runuser="runuser -p -u $user --"
else
    runuser=""
fi

$runuser python3 -m pip install world
$runuser python3 -m pip list --format=columns
$runuser python3 -m pip show world
ls -ld $HOME/.local/lib/python3.*/site-packages/world-*.dist-info
$runuser python3 -m pip uninstall -y world
$runuser python3 -m pip list --format=columns
# Temporarily disabled.  See #912379
#$runuser python3 -m pip list --outdated
if [ $(id -u) = 0 ]
then
    deluser --quiet testing
fi
```

It is apparent that there is a big difference between the two. Both will technically create a pass or a fail, and one might think that the first option, the cloud\_enum control file, seems easier and better to use. However, this is a superficial test which means “The test does not provide significant test coverage, so if it passes, that does not necessarily mean that the package under test is actually functional”. Because of this, we would rather have the python-pip test environment. It is more detailed and includes tests of different types of end-user environments.

We did just throw a bunch of text and code at you all to look at without much explanation, as it was important to note the differences before getting too involved. But lets take a step back now and look more closely at this.

Looking more closely at the `cloud_enum` control file, we have three things going on:

```
Test-Command: cloud_enum --help
Depends: @
Restrictions: superficial
```

The first thing we do is tell what command we are running. Because this is just a superficial test, we do not tell it to run a script and instead just do one line to test if it outputs the help. We then tell it to depend on the same dependencies that the package depends on, by using ‘@’. Should the test need other dependencies, we can list them here. In another test we will look at, this will be seen in action. We finally tell it that yes, this test is just a superficial one. We could tell it other things, like that `cloud_enum` needs root, or that after running this test the testing environment will need to be scrapped.

The next control file we will learn from is [pytest-factoryboy’s](https://gitlab.com/kalilinux/packages/pytest-factoryboy/-/tree/kali/master/debian/tests):

```
Tests: test3-pytest-factoryboy
Depends: @, python3-pytest-pep8
```

As we can see, it depends on a python module. This python module will help us to test the tool, as we can see being done in the test:

```
#!/bin/sh
set -e
cp -r tests "$AUTOPKGTEST_TMP/" && cd "$AUTOPKGTEST_TMP"
for py in $(py3versions -i); do
    $py -Wd -m pytest -v -x tests 2>&1;
done
```

We can also see something else being done that is a good practice. `$AUTOPKGTEST_TMP` can be used during these tests, and will help to clean a system and start on a next test, assuming the `breaks-testbed` flag is not set.

Another package that can show a lot of info is [hyperion](https://gitlab.com/kalilinux/packages/hyperion/-/tree/kali/master/debian/tests). However, due to the size of the files and the breakdowns associated that will not be explained here.

[What to do](broken-reference)

So you have a system set up, have seen tests in practice, but now you need to actually write the tests. Once you find a package that has no test or a superficial test, you should learn the tool. Let us say that we have a tool that pings a server and then depending on the response will tell the user something. What does a fail look like? What does a success look like? Are there any edge cases that might mess up your test?

The next step after learning about a tool’s purpose is to figure out what you will need to tell autopkgtest. Using our tool from the previous example, will it need root to ping properly? What else might need to be done with the machine or environment to get the tool to work? What about after the test? Will there be an output file, and so therefore you should use $AUTOPKGTEST\_TMP?

Once you learn and note what you can test about the tool, you should start to write the test using the best practices and tips given earlier. There are many available resources that stem from those resources, and lots more packages that have solid tests that you can learn from example with if need be.

Given that Kali uses GitLab, you should fork the [source package](https://gitlab.com/kalilinux/packages) where you want to add tests, and add your tests in a new branch. Our GitLab CI configuration should run the autopkgtest, so you can have a look at the output of the pipelines to see whether your tests have been correctly run and whether they succeeded. If they do not work, you can iterate (adding more commits) until you are satisfied with your test scripts.

Once you do get a completed green test, you should submit a merge request since your work is already on GitLab. The [Save & Share](broken-reference) section of contributing to packages gives a good example of this.

For more information on the environment itself, the `autopkgtest-build-qemu` and `autopkgtest-virt-qemu` man pages are beneficial. As are the docs located at `/usr/share/doc/autopkgtest/`.

[Running tests locally](broken-reference)

If it is needed to run the tests locally, it is luckily fairly straightforward but needs some preparation.

We first download the actual testing software and also `vmdb2` which is to create the disk images to be used for the tests:

```
:~$ sudo apt install -y autopkgtest vmdb2
```

We then need to make a directory that can store our images and data:

```
:~$ sudo mkdir /srv/autopkgtest-images/
```

The following command creates a kali-rolling based image that is compatible with autopkgtests, we can now use this image for future tests:

```
:~$ sudo autopkgtest-build-qemu kali-rolling /srv/autopkgtest-images/kali-rolling.img http://http.kali.org/kali
```

Now to run your tests, all you have to do is run the following command: `autopkgtest ~/packages/mytest/ -- qemu /srv/autopkgtest-images/kali-rolling.img` and point to the directory that contains the package you want to test.

There are many other variations which will potentially be needed, and can be found at /usr/share/doc/autopkgtest/README.running-tests.html. It is encouraged to use the GitLab CI however, as many things have the potential to go wrong with local tests and it is easier to get help if needed when using GitLab.
