# Graphical User Interfaces

Although Strato primarily is a service with a text-based user interface (TUI), you may - in some cases - need a graphical user interface (GUI) to do your work. In many other cases, you can manage without. By utilising a technology called "X11 Forwarding" we can launch an application on our Strato instance, but render it's graphics on our local machine.

In the following, we will be guiding you through the process of setting your computer up for this.

Please note that it is not recommended to install a complete [desktop environment](https://en.wikipedia.org/wiki/Desktop_environment) on your instance. Doing so will require large number of additional libraries to be installed and will possibly replace critical system libraries, which will leave you with a very non-standard instance that is prone to errors and security risks, and will be difficult to troubleshoot.

### Why you might need a GUI

* Your work requires you to 


###  Why you might **not** need a GUI





* Having a GUI will require additional memory.

* You have completed the development phase, and now only need to use Strato for the compute power
* You have discovered, that you can connect to your Strato instance from your local computer, using your prefered analysis software, and execute your code through a console there

    * python: `python3 my_analysis.py`
    * R: `Rscript my_analysis.R`
    * Matlab `matlab --nosplash --nodesktop my_analysis.mat` (correct?)

## Setup

We will prepare


### Windows

One way of doing this is to use [**MobaXterm**](https://mobaxterm.mobatek.net/) to connect to your instance, and to add an additional `-X` to your SSH-command, eg.:

```
ssh -i ~/.ssh/<my_private_key> -X ubuntu@10.92.0.zzz
```
You should then be able to launch the application by typing the name of the application, eg. `Rstudio`.


### MacOS

Coming


### Linux

On Linux this will work out of the box.
