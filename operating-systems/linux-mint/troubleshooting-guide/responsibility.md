# Responsibility

An important step in troubleshooting is **responsibility**.

At this stage you’ve already established the following:

* Observation: The computer doesn’t behave the way you expect.
* Expectation: Your expectation is correct.
* Reproducibility: You’re able to reproduce the issue and you have identified the steps to do that.

The goal now is to identify **which component is responsible** for the issue. The best way to find this out is to proceed by elimination.

During the **reproducibility** phase you identified a series of steps necessary to reproduce the issue. You should now try to reduce the number of steps and remove components which might play a role in the issue in order to identify which component actually does.

Here are some examples:

* An application crashes when you run it in Russian… does it also crash in English?
* The computer is slow to boot… is it slow when offline? are there USB devices plugged in?
* The desktop freezes… does it happen with the default configuration? or without 3rd party applets?

Another strategy to identify which component is responsible is to try and reproduce the issue in different environments.

Here are some examples:

* You see an issue in Cinnamon, does it also happen in MATE?
* You see an issue in a particular release, does it also happen in previous releases?
* You see an issue in Linux Mint, does it also happen in Ubuntu?

By identifying what’s common and what’s not, you have a better chance of identifying where the issue lies.

Note

Here’s an example of an issue where the responsible component was identified:“My Nike shoes hurt my right foot every time I walk. I feel no pain with other pairs of shoes, the same socks, the same places, the same amount of time.”

At this stage, you still don’t know enough to understand the **cause** of the issue, but you’re able to successfully identify the component responsible for the issue.

Important

Linux Mint is made up of thousands of software components, many of them developed by very different teams. Identifying the right component is key to knowing which development team might be able to help and where to report an issue.
