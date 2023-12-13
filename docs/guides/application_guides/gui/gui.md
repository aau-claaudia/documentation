# Graphical User Interfaces

Strato applications are most often operated as [headless interfaces](https://en.wikipedia.org/wiki/Headless_computer). This is the most efficient way of distributing computing ressources, and should be sufficient in most cases. In some cases however, you might need a graphical user interface to do the work you need. This is often referred to as a [GUI](https://en.wikipedia.org/wiki/Headless_software). By utilising a technology called "X11 Forwarding" we can launch an application on our Strato instance, but render it's graphics on our local machine. This might however require some setup of your computer. In the following section, we will be taking you through this process.

Please note that this is not a guide on how to install complete [desktop environments](https://en.wikipedia.org/wiki/Desktop_environment). Doing so is not recomended as this will require large number of additional libraries to be installed, whereby critical system libraries might be replaced, leaving you with a very non-standard instance that is prone to errors and security risks, and will be difficult to troubleshoot.

## Setup

Setup will vary based on your operating system.

### Windows

We recommend using [**MobaXterm**](https://mobaxterm.mobatek.net/) to connect to your instance, and that you add an additional `-X` to your SSH-command, eg.:

```
ssh -i ~/.ssh/<my_private_key> -X ubuntu@10.92.0.zzz
```
You should then be able to launch the application by typing the name of the application, eg. `qgis`, and hitting enter.

### MacOS

Go to 

### Linux

As of writing this (late 2023) [Xorg]("https://en.wikipedia.org/wiki/X.Org_Server") is still the dominant display server on most Linux distribution. It is however expected that many distributions will switch over to [Wayland]("https://en.wikipedia.org/wiki/Wayland_(protocol)") in the near future. 
You can check which server you are running with the command: `echo $XDG_SESSION_TYPE`.
If this command outputs `wayland`, you might consider switching over to X11 (which also provides you with additional backwards compatibility). To do this you will need to run `sudo nano /etc/gdm3/custom.conf` and uncomment the line where it says `WaylandEnable=false`. Don't forget to restart the gnome display manager to effectuate the changes with: `sudo systemctl restart gdm3` 
Because this change is still not implemented, we will refrain from providing detailed guides on this. The [Waypie]("https://gitlab.freedesktop.org/mstoeckl/waypipe") project might be able to provide a solution.
