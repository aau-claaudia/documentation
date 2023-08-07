# Transferring files

## Linux & MacOS 
For larger files it can be benefitial to use Rsync, which is preinstalled on MacOS and most Linux-systems. 
Rsync has numerous additional features, like compressing the file during transfer and displaying a progress bar. Can it pick up interrupted transfers?

The basic command structure is:
`rsync <sender> <receiver>


## For Windows Users
If you are a Windows user, we recommend you use [WinSCP](https://winscp.net/) to transfer the files. Do note that WinSCP is also avaialable in the AAU Software Center.

After downloading and installing the application:
1. Choose SCP as the "File protocol"
2. In the field "Host name" type in your IP-adress.
3. For the SSH-protocol the standard "Port number" is 22.
4. The field "User name" is a standard username that gets assigned to your instance. A list of standard usernames can be found here.  
5. By standard the field "Password" can be left empty.
[billede]
6. Click the "Advanced Button". 
7. Navigate to * SSH -> Authentication * and browse to the location of your SSH-key. Select the key and press "Open". 

If you have navigated to the correct location and still can not see your SSH-key, please select "Show all files" as shown in the image below. Note that WinSCP only supports SSH-keys in the PuTTY-format (*.pkk*). If you have not already converted your key to this format, WinSCP will offer to do this for you, when you select the key in *.pem*-format.
8. Press "Ok" in the "Advanced" window to apply these settings.
9. Press login. The first time you login you will be welcomed by a warning message, asking wether you do in fact want to connect to this adress. If you can confirm this is what you are trying to do, you can press Yes.
10. You should now have a two-pane window, split vertically. On the left side you will have your local computer, and on the right side you will have the remote computer. To transfer files between them you can simply drag and drop. 


