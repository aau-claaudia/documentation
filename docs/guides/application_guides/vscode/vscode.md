# Visual Studio Code
[Visual Studio Code]("https://code.visualstudio.com/") (VS Code) is a popular code editor developed by Microsoft. In the following, we will be taking you through the process of installing the application on your Strato instance, and launching the application with a graphical user interace (GUI). The application will be running on your instance, but 


## Install VS Code

First download and install the GPG-key provided by Microsoft. The purpose of a GPG-key is to verify that we are indeed installing the software we are asking for, and that the software has not been tampered with. 

```
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg && sudo install -D -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/packages.microsoft.gpg
```

We then add the Microsoft repository to the list of sources used by the default package manager in Ubuntu: [APT]("https://en.wikipedia.org/wiki/APT_(software)"). 
```
sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'
```
As we have installed the GPG key, we do not need to keep the GPG key floating around in our user directory. Let's delete it:
```
rm -f packages.microsoft.gpg
```

We install installing the following library:
```
sudo apt install apt-transport-https
```
After making these modifications, we will need to update the APT packaging index:
```
sudo apt update
```

We can now install VS Code
```
sudo apt install code
```
## Launch VS Code

Provided that you have prepared your local computer according to our section on [GUI's](""), and you have 

You can launch VS code with: 
```
code
```


