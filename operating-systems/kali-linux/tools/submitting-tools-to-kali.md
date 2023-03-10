# Submitting tools to Kali

[Preparations](broken-reference)

In order for a tool to be added to any Debian-based distribution it needs to be packaged, this can be seen by a Debian/ file in the source code. For developers, we have [documentation](https://www.kali.org/docs/development/public-packaging/) that explains this process should they wish to do this themselves. Keep in mind if this tool is packaged for Debian or not when submitting the tool. Additional information that should be found is the license associated, what dependencies the tool has, what other tools are similar, how active is the development of the tool, and finally how to install the tool.

Once you have the correct information on the tool, a request for the tool to be added should be submitted on our [bug tracker](https://bugs.kali.org/). We have [documentation](https://www.kali.org/docs/community/submitting-issues-kali-bug-tracker/) on how to get started at the bug tracker if needed.

[Requesting the tool:](broken-reference)

1. Report issue
2. Category - New Tool Requests
3. Reproducibility - N/A
4. Severity - minor
5. Priority - normal
6. Summary - Tool name, short description
7.  Description, answer the following questions:

    \[Name] - The name of the tool

    \[Version] - What version of the tool should be added?

    * If it uses source control (such as git), please make sure there is a release to match (e.g. git tag)

    \[Homepage] - Where can the tool be found online? Where to go to get more information?

    \[Download] - Where to go to get the tool? either a download page or a link to the latest version

    \[Author] - Who made the tool?

    \[Licence] - How is the software distributed? What conditions does it come with?

    \[Description] - What is the tool about? What does it do?

    \[Dependencies] - What is needed for the tool to work?

    \[Similar tools] - What other tools are out there?

    \[Activity] - When did the project start? Is is still actively being deployed?

    \[How to install] - How do you compile it?

    * Note, using source code to acquire (e.g. git clone/svn checkout) can’t be used - Also downloading from the head. Please use a “tag” or “release” version.

    \[How to use] - What are some basic commands/functions to demonstrate it?

    \[Packaged] - Is the tool already packaged for Debian?
8. Submit issue
