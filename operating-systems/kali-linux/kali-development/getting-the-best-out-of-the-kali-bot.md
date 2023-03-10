# Getting the best out of the Kali Bot

Kali is putting lots of efforts in building automation to help maintain an ever bigger number of packages of security tools. This article presents the Kali Bot, how it works and the few points to pay attention to so that the Kali Bot can do its job.

[Introduction](broken-reference)[What is the Kali Bot?](broken-reference)

The Kali Bot is actually an instance of the [Debian Janitor Bot](https://salsa.debian.org/jelmer/debian-janitor/) developed by Jelmer Vernooij. Our instance runs on [janitor.kali.org](https://janitor.kali.org/) and controls the [kali-bot](https://gitlab.com/kali-bot) GitLab account to be able to push changes and submit [merge requests](https://gitlab.com/groups/kalilinux/packages/-/merge\_requests) to our packaging repositories.

[What can it do?](broken-reference)

It has many features but we currently use three of them:

1. it can push small fixes/improvements to packaging git repositories, this is the [lintian-fixes](https://janitor.kali.org/lintian-fixes/) task;
2. it can automatically package new upstream releases in the [kali-experimental](https://www.kali.org/docs/general-use/kali-branches/) repository and propose the corresponding merge request in the git repository, this is the [fresh-releases](https://janitor.kali.org/fresh-releases/) task;
3. it can automatically package git snapshots in [kali-bleeding-edge](https://www.kali.org/docs/general-use/kali-bleeding-edge/) every time that the upstream developers have pushed a change to their git repository, this is the [fresh-snapshots](https://janitor.kali.org/fresh-snapshots/) task.

[Information for upstream developers](broken-reference)

Dear infosec developers, Kali wants to provide the best experience to the users of your software and as such we strive to provide the latest version (with the help of the Kali Bot)!

[Recommendations](broken-reference)

Following the recommendations below maximizes your chances that the Kali Bot will be able to prepare a working package out of your releases (and git snapshots).

* Maintain your software in a public git repository. It seems obvious but we still have software only released as a tarball.
* Create and push git tags for your releases. We monitor new upstream releases with a tool called [uscan](https://manpages.debian.org/uscan), it follows the instructions provided in `debian/watch` in our packaging repositories. That file typically points to the “tags” or “releases” page of your git hosting and uscan will parse the HTML to find out the URL of the latest release tarball.
* Don’t build release tarballs that differ significantly from git snapshots. Ideally the packaging rules should be applicable to both release tarballs and those generated with `git archive`.
*   Always provide some build system (even if you have nothing to build) so that you control the instructions to install your software in a system-wide manner. If you don’t, then the installation instructions are encoded in the Kali package and any automated package update will try to apply the former instructions to your latest version and they might not work if you have made significant changes.

    Note that the build system should offer a way to install the files in a non-standard place. With a Makefile, the package build typically calls `make install DESTDIR=$(pwd)/debian/tmp` to install the files in a temporary directory that gets packed up in the `.deb` file without interfering with the root file system (doing so would cause the build to fail as it doesn’t have the required permissions). Have a look at [dnsenum](https://salsa.debian.org/pkg-security-team/dnsenum) for an example with a simple Makefile.

[How to get timely updates in kali-bleeding-edge](broken-reference)

The Kali Bot has many packages to monitor and it might take a while to notice that you have pushed some changes to your git repository. If you want the bot to have a look at your repository immediately, then configure a webhook notifying `https://janitor.kali.org/` of your push events.

For GitHub, you can do so in the “Webhooks” section of the “Settings” tab. Fill the form as shown below and click on “Add webhook”:

[![](<../../../.gitbook/assets/github webhook.png>)](<../../../.gitbook/assets/github webhook.png>)

Thanks to this, you can point users who reported bugs to the [kali-bleeding-edge documentation](https://www.kali.org/docs/general-use/kali-bleeding-edge/) and ask them to verify that their issues is effectively fixed in the package available in kali-bleeding-edge.

If you have setup the webhook, and if you don’t see any updated package in the kali-bleeding-edge repository, you might want to read on the rest of this page to see if you can figure out what’s wrong. If you’re stuck, feel free to reach us at [\[email protected\]](https://www.kali.org/cdn-cgi/l/email-protection#e0848596858ca08b818c89ce8f9287) and we will do our best to fix this for you.

[Information for Kali developers](broken-reference)

The Kali Bot is still relatively young and there are many things that can go wrong in the various tasks that it runs. In this section, we try to show where you can look to try to understand why the bot didn’t do what you expected.

[Discovering the web interface](broken-reference)

The [basic web interface](https://janitor.kali.org/) shows you the result of the latest run of each task on each package and gives some factual information about the result and about how to access the build result.

There’s [another web interface](https://janitor.kali.org/cupboard/), named cupboard, which gives more information (and control) about what’s going on in the backend. You can look at the queue of upcoming jobs, the history of recently executed jobs, job results that are waiting to be published, jobs waiting human approval before publication, etc.

Various pages give you the possibility to send instructions to the Kali Bot with different buttons. However clicking on the buttons will only have an effect if you are connected with your gitlab.com account and if you are a member of the [kalilinux/packages](https://gitlab.com/groups/kalilinux/packages/-/group\_members) group.

[Understanding Kali Bot’s workflow](broken-reference)

There’s a scheduler that will regularly trigger all possible jobs on all possible packages (the allowed combinations are defined in the publish-policy.json file.

* that file is only accessible to Kali developers). You can see the [resulting queue](https://janitor.kali.org/cupboard/queue).

Then we have a worker that runs all those jobs. A job is usually a run of `debian-svp` (a command within `silver-platter`) which is a tool to automate some changes on packaging git repositories.

Once the change is done, the bot will rebuild the package with the added change, ensure that the package still builds and compare the generated packages with the result of the build of an unmodified package.

At this stage, if the package built successfully, the change is considered “ready” and it will appear in the [corresponding web page](https://janitor.kali.org/cupboard/ready) until it has been merged in the target repository (or until it has become obsolete).

Once built, the change will be put in a queue to be published. It will usually happen soon but it can be delayed due to rate limits (the bot publishes results at a slow pace so that any mistake can be caught before it has impacted too many repositories, and so that developers do not get instantly overwhelmed). You can avoid those restrictions with the “Publish now” button in the corresponding job page.

[Things to know about lintian-fixes](broken-reference)

This job is the easier to reproduce and is quite unlikely to fail. It’s just running the [lintian-brush](https://salsa.debian.org/jelmer/lintian-brush) tool within the packaging git repository.

When the tool isn’t able to fix something, it just does nothing without failing. Also in its default configuration, the tool only fixes something when there’s a single obviously correct fix. It will not make opinionated choice in place of the maintainer.

In the Kali context, the job should not document its work in `debian/changelog`, as it detects that we are updating `debian/changelog` in standalone commits with `gbp dch`. If the recent history did update the changelog along with each change, then the bot will follow along (you can disable that behaviour in your manual run with the `--no-update-changelog` command line option).

The publish policy configured in Kali lets the bot directly push those changes to the packaging git repositories (in other words, it will not submit merge requests).

[Things to know about fresh-releases](broken-reference)

This job will run `uscan` to check whether there’s a new upstream version of the software that is not yet in the git packaging repository. If it finds a newer version, it will import it with `gbp import-orig` and update the changelog with `gbp dch`.

You can reproduce all this locally by running `debian-svp new-upstream --debian-revision=0kali1 --require-uscan --refresh-patches --dry-run --skip-empty --diff <package>` on a kali-rolling system with the appropriate `deb-src` line in APT’s sources.list (and with `silver-platter` installed).

The publish policy configured in Kali lets the bot directly push the updates for the `upstream` and `pristine-tar` branches, but the changes for the `kali/master` branch will be proposed with a merge request. At the same time, the resulting package will also be uploaded to `kali-experimental`.

The main downside at the current time is that the bot will thus do nothing if there’s a new upstream release that doesn’t build with the current packaging (because we need to update our packaging rules). How to improve this situation is tracked in [this ticket](https://github.com/jelmer/janitor/issues/93).

[Things to know about fresh-snapshots](broken-reference)

This job will try to build an updated package based on the latest upstream git commit. To achieve this, it first tries to identify the upstream git repository by looking at the `Homepage` field in `debian/control` and/or the `Repository` field in `debian/upstream/metadata`.

Once it has found this repository, it will create an updated upstream tarball with `git archive`. The version given to that tarball will look like `<ver>+git<date>.<n>.<commit>` where `<ver>` is the latest upstream version, `<date>` is the date of the last commit, `<n>` is a numerical increment in case we have multiple updates during the same day, and `<commit>` is a short commit identifier to be able to know exactly what commit has been packaged.

Then it will `gbp import-orig` that new upstream tarball and update the changelog with `gbp dch`.

You can reproduce all this locally by running `debian-svp new-upstream --snapshot --dry-run --diff <package>`.

The publish policy configured in Kali will just upload the resulting package to `kali-bleeding-edge`. The git repository changes are not pushed anywhere at this time (except on the bot’s own git repository that can be accessed in [janitor.kali.org/git/](https://janitor.kali.org/git/)).

[So why didn’t the Kali Bot do its job?](broken-reference)

* Maybe it did build the changes, but the job has not been published yet due to rate-limiting. Check the list of changes which are [ready to be published](https://janitor.kali.org/cupboard/ready).
* Maybe it failed, have a look at the logs of the jobs for the package that you are interested in. The `/cupboard/pkg/<package>` URL should be your starting point (ex: [amass](https://janitor.kali.org/cupboard/pkg/amass/). Then look at the recents runs of and find the latest run of the job that you are interested in.
* If you find something odd, that doesn’t make sense or that looks wrong, feel free to report it to [\[email protected\]](https://www.kali.org/cdn-cgi/l/email-protection#c0a4a5b6a5ac80aba1aca9eeafb2a7) or [directly to the janitor maintainer](https://github.com/jelmer/janitor/issues/new) if you think that it’s a generic issue with the bot.

[Special thanks](broken-reference)

We would like to give a big shout-out to [Jelmer Vernooij](https://www.jelmer.uk/) who wrote the Janitor Bot in the first place, but also worked very hard with us to customize the bot for our needs and to fix the numerous issues that [we reported to him](https://salsa.debian.org/jelmer/debian-janitor/-/issues?label\_name%5B%5D=kali).
