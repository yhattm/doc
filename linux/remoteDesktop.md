<pre>
Issue
Initiating a connection to an Amazon EC2 Linux instance with desktop functionality using PuTTy provides terminal access but does not permit access to desktop functionality.
 
Short Description
This article describes how to connect to an Amazon EC2 Linux instance desktop by using Windows Remote Desktop.
 
Resolution
Complete all steps described in the article How can I use AWS to quickly create and connect to an Amazon EC2 Linux instance?
 Note
 For purposes of this article, make sure that you are running an instance of Ubuntu 14.04 LTS (Trusty Tahr) as described in the related article. In addition, this article assumes the user name is 'ubuntu'; if you're using a different user name, make the appropriate substitutions (in steps 7, 8, 12, 17, and 18).
 
Connect to your Linux instance as described in Connecting to Your Linux Instance from Windows Using PuTTy.
Run the following commands from the terminal to install updates, an upgrade, and install additional packages.
      sudo apt-get update
      sudo apt-get upgrade
Because you will be connecting from Windows Remote Desktop, edit the sshd_config file on your Linux instance to allow password authentication.
      sudo vim /etc/ssh/sshd_config
Change PasswordAuthentication to yes from no, then save and exit.
 Note
 After making this change, press SHIFT+ : [colon] to open a new command entry box in the vim editor. Type wq, and then press Enter to save changes and exit vim.
Restart the SSH daemon to make this change take effect.
      sudo /etc/init.d/ssh restart
Temporarily gain root privileges and change the password for the ubuntu user to a complex password to enhance security. Press the Enter key after typing the command passwd ubuntu, and you will be prompted to enter the new password twice.
      sudo –i
      passwd ubuntu
Switch back to the ubuntu user account and cd to the ubuntu home directory.
      su ubuntu
      cd
Install Ubuntu desktop functionality on your Linux instance, the last command can take up to 15 minutes to complete.
      export DEBIAN_FRONTEND=noninteractive
      sudo -E apt-get update
      sudo -E apt-get install -y ubuntu-desktop
Install XRDP and other xfce4 resources.
      sudo apt-get install xfce4 xrdp
      sudo apt-get install xfce4 xfce4-goodies
 
Make xfce4 the default window manager for RDP connections.
      echo xfce4-session > ~/.xsession
Copy .xsession to the /etc/skel folder so that xfce4 is set as the default window manager for any new user accounts that are created.
      sudo cp /home/ubuntu/.xsession /etc/skel
Open the xrdp.ini file to allow changing of the host port you will connect to.
      sudo vim /etc/xrdp/xrdp.ini
Look for the section [xrdp1] and change the following text (then save and exit [:wq]).
      port=-1
      - to -
      port=ask-1
Restart xrdp.
      sudo service xrdp restart
On Windows, open the Remote Desktop Connection client, paste the fully qualified name of your Amazon EC2 instance for the Computer, and then click Connect.
When prompted to Login to xrdp, ensure that the sesman-Xvnc module is selected, and enter the username ubuntu with the new password that you created in step 7. When you start a session, the port number is -1.
When the system connects, several status messages are displayed on the Connection Log screen. Pay close attention to these status messages and make note of the VNC port number displayed. If you want to return to a session later, specify this number in the port field of the xrdp login dialog box.


Note: To make sure desktop icons appear correctly in xfce4, select an icon set other than GNOME. On the Applications menu, click Settings, and then click Appearance. Select an icon set, and then click Close.
</pre>