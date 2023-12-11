# Matlab

There are two ways in which you can work with Matlab on Strato instances.

1. **Run with graphical user interface (GUI):** Here the application runs on your Strato instance, but it's graphics are rendered on your local computer. This is useful for interactive development, ie. workflows where you will need to test and modify your code continuously. Make sure to prepare your local computer accordingly, by following our section on [Graphical User Interfaces]("../gui/gui.md"). 
2. **Run the application in headless mode:** By default Strato instances do not come with any graphical user interfaces, but are operated in headless mode. In cases where you simply need to execute a prewritten script, this approach might be preferable.

**Bonus tip:** Matlab is also available on [DeiC Interactive HPC]("https://cloud.sdu.dk/") (UCloud) which ships with a GUI out of the box. Read more about this possibility in [the official platform documentation]("https://docs.cloud.sdu.dk/Apps/matlab.html#connect-to-a-network-license").


##  Installing Matlab


Begin by updating the APT packaging index, so we have an updated list of sources to download applications from:

```
sudo apt update
```

Before going further, we will need to install an unzip tool and some additional libraries recommended by Mathworks.
```
sudo apt install unzip libx11-dev xorg-dev
```

Download the Matlab Package Manager (MPM) from Mathworks and make it executable:
```
sudo wget -P /usr/local/bin/ https://www.mathworks.com/mpm/glnxa64/mpm && sudo chmod +x /usr/local/bin/mpm
```

Now install Matlab using MPM. Note that here we are installing a version from late 2023. You can check [Mathworks website]("https://se.mathworks.com/help/matlab/release-notes.html") to see if there is a newer release.
```
mpm install MATLAB --release=R2023b --destination=~/matlab/
```

As we want to be able to launch matlab, when we type `matlab` - we will need to add the directory of the matlab executable to our `PATH` variable. We do this and restart our shell:
```
echo "export PATH=~/matlab/bin:$PATH" >> .bashrc && exec $SHELL
```

## Registering 
Matlab is licensed software, and we will therefore need to register the applicaiton, before we can start using it. Note that this process may run very slowly, and therefore it is advisable to have some patience with this step.

* Run the command `activate_matlab.sh`. This will launch a "Software Activation" window.
* Choose: "Activate automatically using the Internet"
* In your internet browser go to: [mathworks.com/mwa/otp]("https://mathworks.com/mwa/otp")
* Enter your AAU email and get the one time password (OTP).
    * Note that there is no need to sign up with Mathworks for this process.Mathworks will generate an OTP based on the domain of the email adress.
* Head back to the Activation window we had open earlier.
* Enter your AAU email adress and the OTP you retrieved from the [Mathworks OTP site]("https://mathworks.com/mwa/otp")
* Click "Next".
* Select the appropriate license
    * Students should select "Student license" and Employees "Campus license".
* Complete this process by pressing "Next".
* You will be asked to send you information to Mathworks. Press "Confirm".
 
## Run with GUI

This will launch the familiar Matlab application window (provided that you have followed our section on [setting up Graphical User Interfaces]("https://se.mathworks.com/help/matlab/ref/commandwindow.html")).
```
matlab -desktop
```

## Run in headless mode
If you wanted to run prepared script called `my_script.m`, you would run:

```
matlab -batch my_script
```

If you would want to enter the Matlab console to execute individual statements:
```
matlab -nodisplay
```
