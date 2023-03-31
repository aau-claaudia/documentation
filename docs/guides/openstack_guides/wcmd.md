# Connect to instance from Windows (using OpenSSH)

Most recent versions of Windows come with OpenSSH pre-installed. This allows you to connect to your Strato instance in Windows' native terminal emulator "Powershell". 

To confirm whether you have OpenSSH installed on your machine simply type `ssh` in the command prompt. If it is present on your machine, you will be presented with a printing of the options for the command. If it is not present, you would see an error. If you wish to install it, please follow [this guide](https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse) written by Microsoft. 

## 

1. First create a key (as described in the [quick start guide](../quick-start.md)) and save it as "yourPersonalKey.pem"
2. Locate "yourPersonalKey.pem" using File Explorer.
3. Right click "yourPersonalKey.pem" and select Properties > Security > Edit and remove all users that are not you, SYSTEM or Administrator.
4. Open Powershell (find it in Start Menu > Windows Powershell) and type the following:

```bash
ssh ubuntu@<your floating IP> -i <yourPersonalKey.pem>
```
e.g.
```bash
ssh ubuntu@130.226.98.166 -i yourPersonalKey.pem
```
Do note that you need to either navigate to the folder holding your SSH-key, or provide the path as a prefix for the name of your key. Like so:
```bash
ssh ubuntu@130.226.98.166 -i C:\Users\Anders\.ssh\youPersonalKey.pem
```
You should now have reached your instance. If this approach does not work for you, we recomend that you try using [Putty](./putty.md).

**Additional information:**

- If you wish to use applications with a graphical user interface, Putty is more suitable. This is because Powershell does not support *X-forwarding* which is required for rendering graphics and sending them to a remote machine.
