# Discovering Problems With Download Speed

[How our downloads work](broken-reference)

Kali Linux operates off of a network of [community](https://www.kali.org/docs/community/kali-linux-mirrors/) and official mirrors. What this means is that when you click to [download](https://www.kali.org/get-kali/) Kali Linux there are some steps that are done before you actually begin the download. First you hit [cdimage.kali.org](http://cdimage.kali.org/README.mirrorlist) which is our redirector. This determines where the request is coming from and will send you to one of the best mirrors for your situation. For example, if you are in the US you may get send to Berkley University’s mirror. After you are sent to the best mirror your download request is submitted to it, and your download actually begins.

[Determining which mirror we are at](broken-reference)

Now that we know how this happens we can determine which mirror we are actually getting sent to ourselves. We can do this in a couple of different ways. The first is to simply click [download](https://www.kali.org/get-kali/) and then in the downloads tab right click the download and copy the URL. This works for the majority of web browsers. The second option is to use `curl`:

```
:~$ curl https://cdimage.kali.org/kali-2022.4/kali-linux-2022.4-installer-amd64.iso
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>302 Found</title>
</head><body>
<h1>Found</h1>
<p>The document has moved <a href="https://kali.download/base-images/kali-2022.4/kali-linux-2022.4-installer-amd64.iso">here</a>.</p>
<hr>
<address>Apache/2.4.10 (Debian) Server at cdimage.kali.org Port 443</address>
</body></html>

:~$
```

Here we can see that we were redirected to `kali.download`.

[Submitting bugs](broken-reference)

If the download speed is noticeably slow or the mirror is not working, we would love to know. This can be the result of a few different problems and none of them are able to be fixed without us knowing which mirror and what speeds. So lets get that information wrapped up nicely.

We can use `wget` to download the iso file and learn just how fast the download is taking. If we are on Windows, we can either get the download speed from the web browser or install [wget for Windows](https://medium.com/nerd-for-tech/using-wget-command-in-windows-10-environment-d766b8f526e9)

```
:~$ wget https://kali.download/base-images/kali-2022.4/kali-linux-2022.4-installer-amd64.iso
--2022-07-15 15:56:17--  https://kali.download/base-images/kali-2022.4/kali-linux-2022.4-installer-amd64.iso
Resolving kali.download (kali.download)... 104.18.103.100, 104.18.102.100, 2606:4700::6812:6764, ...
Connecting to kali.download (kali.download)|104.18.103.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2944139264 (2.7G) [application/octet-stream]
Saving to: ‘kali-linux-2022.4-installer-amd64.iso’

kali-linux-2022.4-installer-amd64.iso   6%[====>                                                                     ] 196.46M  31.6MB/s    eta 81s

:~$
```

As we can see we are downloading at about 31.6MB/s and we are using the mirror link we got from the previous section.

Lets look at another example, this time with a connection from France:

```
:~$ curl https://cdimage.kali.org/kali-2022.4/kali-linux-2022.4-installer-amd64.iso
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>302 Found</title>
</head><body>
<h1>Found</h1>
<p>The document has moved <a href="https://archive-4.kali.org/kali-images/kali-2022.4/kali-linux-2022.4-installer-amd64.iso">here</a>.</p>
<hr>
<address>Apache/2.4.10 (Debian) Server at cdimage.kali.org Port 443</address>
</body></html>

:~$ wget https://archive-4.kali.org/kali-images/kali-2022.4/kali-linux-2022.4-installer-amd64.iso
--2022-07-15 16:09:44--  https://archive-4.kali.org/kali-images/kali-2022.4/kali-linux-2022.4-installer-amd64.iso
Resolving archive-4.kali.org (archive-4.kali.org)... 176.31.228.102
Connecting to archive-4.kali.org (archive-4.kali.org)|176.31.228.102|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2944139264 (2.7G) [application/octet-stream]
Saving to: ‘kali-linux-2022.4-installer-amd64.iso.1’

kali-linux-2022.4-installer-amd64.iso   0%[                                                                          ] 615.75K   610KB/s

:~$
```

Now that we know the download speed and the mirror link we can submit a [bug report](https://www.kali.org/docs/community/submitting-issues-kali-bug-tracker/) with all our information.

[Using a different mirror](broken-reference)

We can consult back to the [community](https://www.kali.org/docs/community/kali-linux-mirrors/) mirrors and manually select a different mirror to see if our download speed improves. To do this we simply will copy the mirror link we want to use from the list and then change “README” to be `kali-2022.4/kali-linux-2022.4-installer-amd64.iso` or whichever download link we are using. We can see this in the previous section, right after `kali-images/`.
