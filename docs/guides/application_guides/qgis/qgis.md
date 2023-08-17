# QGIS

QGIS is a free and open source geographic information system (GIS) used for working geospatial data. In the following sections we will demonstrate how to setup QGIS on your Strato instance. As this is an application that relies heavily on having a graphical user interface (GUI), we will be using a technology called "X11 Forwarding" to receive the graphics signal from the Strato instance and display them on your local machine. Please read through the section on [**Graphical User Interfaces**](url) to ensure that your local computer is set up for this.

In the following we will be demonstrating two ways of installing QGIS:

- [Install using apt](#install-using-apt): This uses the builtin package manager and requires no additional software. This is the best option for most people.
- [Install using conda](#install-using-conda): This allows for having more than one version of QGIS in an isolated environment. If you already know how to use conda, this approach might be preferable. 

## Install using APT

One way to install QGIS is to use the package manager `apt` found on all Debian-based GNU/Linux distributions - including Ubuntu. This section assumes that your Strato instance is running Ubuntu 22.04. You can use the command `lsb_release -ds` to check your distribution. 

We will begin by downloading a GPG-keyring. This will allow apt to verify the integrity of the software we will be downloading. 
```
sudo wget -O /etc/apt/keyrings/qgis-archive-keyring.gpg https://download.qgis.org/downloads/qgis-archive-keyring.gpg
```

We will then create a file that specifies our system requirements and which repository we want download from. 

We will use a built-in text editor called `nano` to edit the file. 

```
sudo nano /etc/apt/sources.list.d/qgis.sources
```

Copy and paste the following text into the file:
```
Types: deb deb-src
URIs: https://qgis.org/ubuntu-ltr
Suites: jammy
Architectures: amd64
Components: main
Signed-By: /etc/apt/keyrings/qgis-archive-keyring.gpg
```
Then save the file:
Press `ctrl + x` to exit, `Y` to confirm you wish to save the changes, and finally hit `enter` to confirm the filename. 

After making all these changes, we will need to update apt:
```
sudo apt update
```

We then have apt download and install QGIS:
```
sudo apt install qgis
```

QGIS should now be installed on the instance. 

Launch the application by typing:
```
qgis
```

## Install using Conda

Some users may need to have different versions of QGIS for different research projects. Conda offers a very elegant solution for this.
Please refer to our section on [**Anaconda**](../anaconda/anaconda.md) to learn more about conda.

Create a conda environment - here we will call it *my_gis_project* - feel free to choose another name:
```
conda create --name my_gis_project
```

Activate the conda environment:
```
conda activate my_gis_project
```

Install download QGIS (from the channel *conda-forge*)
```
conda install -c conda-forge qgis
```

And launch the application:
```
qgis
```
