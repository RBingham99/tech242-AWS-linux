## Creating AMI's

1) To create an AMI you first need to create an instance of a VM with user data.

2) Then once it is running we need to create an AMI image from it by clicking on the instance ID.

3) Then the "actions" button.

4) Then the "image and templates" option.

5) And then the "create image" option.

6) We then need to give the the AMI a name.

7) Then click on "new tag" at the bottom, and type "Name" in the key field and copy the name of the AMI into the value field.

8) Then click "launch".

9) Now go to the image id, then click "Launch instance from AMI".

10) We then need to make an instance just like before but we don't need to specify the AMI as it is already the one we want.

11) Then when you get to the "user data" textbox at the bottom you only need to put in the shebang `#!/bin/bash` and the commands to navigate files and run the app, as we no longer need to do any installs.

12) Click on "Launch" and your new instance will launch and load up much faster.