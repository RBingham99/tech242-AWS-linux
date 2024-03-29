## Accessing your VM

# Steps to access your VM
1) First you need to save the .pem file that you either got earlier when you created your key pair or you should be able to get from your manager or system admin. We need to save this file in your .SSH folder, to do this simply right-click on the file wherever it currently is, select cut, then navigate to your .SSH folder (if you are on mac press cmd + shift + . to show hidden folders) and paste the file in. 
2) Open your .SSH folder with your terminal and type `ls` and make sure the .pem file is in there, if it is use the command `chmod 400` followed by the name of your .pem file. This will change the permissions of the file.
3) Now navigate to your instance on AWS and click connect in the top right hand corner (you will need to start your instance if you haven't already), then select the "SSH client" tab and copy the last line in the instructions, it will start with `ssh -i` followed by the name of your .pem file and then the name of the OS you chose when you selected your AMI. In your terminal paste in that command.
4) If it is the first time you are connecting to your VM it will want you that it cannot establish the authentisity of the connection, just enter "yes" and you will connect to your VM.
5) You are now connected to your VM!