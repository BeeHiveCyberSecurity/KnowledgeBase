# Environment

Your settings, your locale, the set of applications you’ve installed and everything that might make things on your computer unique, or somewhat different than on somebody else’s, is called your **environment**.

If the issue is always reproducible on your computer but the very same steps do not trigger it on other computers, then the environment is key and the differences between the environment of the two computers should be reviewed.

Important

When other people can’t reproduce your issue with the steps you provided, give them more information about your environment.

Depending on the nature of the issue, you might look at different parts of the environment.

### Locale[¶](broken-reference)

Your locale consists of your language and regional settings.

Here are a few common issues related to locales:

* Crashes due to a bad translation.
* Missing translations.
* Crashes due to unicode characters.
* Wide widgets or applications due to long translations.
* Failure to show special characters.

When an issue is specific to your locale, set your language to English, log out and log back in again, and see if the issue is still happening.

To see or share details about your locale, open a terminal and type `locale`.

### List of packages[¶](broken-reference)

An issue might happen because of a missing package or a missing library.

You can use the terminal to search. For instance, to search for the foobar library, type `apt search foobar`.

To see or share the list of installed packages on your system, type `dpkg -l`.

You can also check the version of a particular package. To check the installed and available versions of cinnamon for instance, you can type `apt policy cinnamon`.

Last but not least, you can list your repositories with `inxi -r`.
