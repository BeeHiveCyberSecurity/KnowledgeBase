# Configure TigeVNC on Athena OS

In several scenarios, like container or WSL images, users would like to connect to Athena OS environment by an external client. Here it is explained how to configure Athena OS as a VNC server by using TigerVNC.

[TigerVNC](https://wiki.archlinux.org/title/TigerVNC) is an implementation of the **Virtual Network Computing (VNC)** protocol.

## Configure the VNC server

Login to Athena OS environment and let's guess your user account is named `athena`. It will be the user account that will be configured for accessing to the Athena VNC server.

Athena OS container and WSL have already `tigervnc` installed. If not, run:
```
sudo pacman -Syu --noconfirm --needed check imlib2 tigervnc libxrandr fuse libfdk-aac ffmpeg nasm xorg-server xorg-server-devel
sudo pacman -Syu --noconfirm --needed xrdp xorgxrdp
```

Once everything has been installed, the Athena VNC server needs to be configured:
1. Create a password using `vncpasswd` which will store the hashed password in `~/.vnc/passwd`.
2. Edit `/etc/tigervnc/vncserver.users` to define user mappings. Each user defined in this file will have a corresponding port on which its session will run. The number in the file corresponds to a TCP port. By default, :1 is TCP port 5901 (5900+1). If another parallel server is needed, a second instance can then run on the next highest, free port, i.e 5902 (5900+2). In our example, `/etc/tigervnc/vncserver.users` should be similar to:
   ```
   # TigerVNC User assignment
   #
   # This file assigns users to specific VNC display numbers.
   # The syntax is <display>=<username>. E.g.:
   #
   # :2=andrew
   # :3=lisa
   :2=athena
   ```
   It means that `athena` user is assigned to the `$DISPLAY=:2` and the VNC server will expose the VNC `athena` session on `5902` port.
3. Create `~/.vnc/config` and at a minimum, define the type of session desired with a line like `session=foo` where `foo` corresponds to whichever desktop environment is to run. One can see which desktop environments are available on the system by seeing their corresponding `.desktop` files within `/usr/share/xsessions/`. In our example:
   ```
   session=gnome-xorg
   geometry=1920x1080
   #localhost
   alwaysshared
   ```

Start an instance of the `vncserver@.service` template and optionally enable it to run at boot time/shutdown. Note that the instance identifier in this case is the display number (e.g. instance `vncserver@:2.service` for display number :2). In our scenario, `athena` is assigned to the display `:2`, so the VNC server must be started by systemd in the following manner:
```
sudo systemctl start vncserver@:2.service
```
If no messages are shown, it should work. For checking if error was not produced, check the output of `status` argument of systemd. The no error result should show:
```
sudo systemctl status vncserver@:2.service
● vncserver@:2.service - Remote desktop service (VNC)
     Loaded: loaded (/usr/lib/systemd/system/vncserver@.service; disabled; preset: disabled)
     Active: active (running) since Thu 2023-03-23 19:49:15 CET; 28min ago
    Process: 940 ExecStart=/usr/bin/vncsession-start :2 (code=exited, status=0/SUCCESS)
   Main PID: 947 (vncsession)
      Tasks: 0 (limit: 9430)
     Memory: 716.0K
     CGroup: /system.slice/system-vncserver.slice/vncserver@:2.service
             ‣ 947 /usr/bin/vncsession athena :2

Mar 23 19:49:15 DESKTOP-LV4580H systemd[1]: Starting Remote desktop service (VNC)...
Mar 23 19:49:15 DESKTOP-LV4580H systemd[1]: Started Remote desktop service (VNC).
```
In case you get an error, or a message related to the deactivation of the VNC service, check the `.log` file in `~/.vnc/` folder. The VNC server for `athena` user runs correctly if the `~/.vnc/<your-hostname>.log` file will end with the following strings:
```
Loading xinit script /etc/X11/xinit/xinitrc.d/50-systemd-user.sh
Loading xinit script /etc/X11/xinit/xinitrc.d/90xbrlapi
X session wrapper complete, running session /usr/bin/gnome-session

Thu Mar 23 19:49:17 2023
 ComparingUpdateTracker: 0 pixels in / 0 pixels out
 ComparingUpdateTracker: (1:-nan ratio)
```
Until now, the Athena VNC server is exposed on the `5902` port. If you would like to bind the VNC server on the `5900` default port, and you don't want to use a password for authenticating to the VNC server, you can bind the VNC server to the default port by:
```
x0vncserver -SecurityTypes none -display :2
```
where `-SecurityTypes none` prevents the usage of password for authenticating to the VNC server on the default port `5900`, and `-display :2` specifies the running display to be shown on this VNC session.

## Connect by a VNC client

Now, it is the time to use a VNC client for connecting to Athena VNC server.

### Windows VNC client
If you are on Windows, you can use [VNC Viewer](https://www.realvnc.com/en/connect/download/viewer/). Install it and connect to the Athena VNC server by typing the Athena IP address. If you didn't bind the VNC server to the default port as explained above, you must specify the `5902` port, and it will ask you the password set at the beginning by `vncpasswd` command:
![image](https://user-images.githubusercontent.com/83867734/227327462-5d259dea-b93c-4c26-9da1-d8ad760827ba.png)

### Linux VNC client
If you are on Linux, you can use [Remmina](https://remmina.org/). Install it and connect to the Athena VNC server by typing the Athena IP address. If you didn't bind the VNC server to the default port as explained above, you must specify the `5902` port, and it will ask you the password set at the beginning by `vncpasswd` command.
