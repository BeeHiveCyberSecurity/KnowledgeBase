# Official Kali Linux Docker Images

Kali provides official Kali Docker images that are updated once a week on [Docker Hub](https://hub.docker.com/u/kalilinux/). You can thus easily build your own Kali containers on top of those that we provide. We offer various images to try and suit your needs, all with a different variation of Kali Linux as they use unique [branches for the source](https://www.kali.org/docs/general-use/kali-branches/).

Please note, **all the images below do not come with the “default”** [**metapackage**](https://www.kali.org/docs/general-use/metapackages/). You will need to `apt update && apt -y install kali-linux-headless`.

Here’s a quick review of the various images available (for more detailed information, see our [branch](https://www.kali.org/docs/general-use/kali-branches/) page). First those that you might reasonably want to use:

* [**kalilinux/kali-rolling**](https://hub.docker.com/r/kalilinux/kali-rolling) **is the main image that you should likely use**, tracking the continuously-updated `kali-rolling` package repository, just like the default images.
* [kalilinux/kali-last-release](https://hub.docker.com/r/kalilinux/kali-last-release) is built from the `kali-last-snapshot` repository, it is tracking the last versioned release (e.g. 2019.4, 2020.1, etc.) and will not get any update until the [next release](https://www.kali.org/releases/).

And those that you will likely not need except in very special cases:

* [kalilinux/kali-bleeding-edge](https://hub.docker.com/r/kalilinux/kali-bleeding-edge) is exactly like `kalilinux/kali-rolling` with the [“kali-bleeding-edge” repository](https://www.kali.org/blog/bleeding-edge-kali-repositories/) enabled.
* [kalilinux/kali-experimental](https://hub.docker.com/r/kalilinux/kali-experimental) is exactly like `kalilinux/kali-rolling` with the `kali-experimental` repository enabled. Might be useful to test some not-yet-ready updates uploaded to “kali-experimental” by Kali developers who are looking for feedback.
* [kalilinux/kali-dev](https://hub.docker.com/r/kalilinux/kali-dev) is an image tracking the `kali-dev` repository used by Kali developers to merge updates coming from Debian and changes maintained by Kali Linux. It can be useful to rebuild (or do test rebuild of) Kali packages.

If you want to improve our official Docker images, have a look at the [kali-docker project](https://gitlab.com/kalilinux/build-scripts/kali-docker/) in [our GitLab](https://gitlab.com/kalilinux). We use [GitLab CI](https://gitlab.com/kalilinux/build-scripts/kali-docker/pipelines) to automate the build of our Docker images.
