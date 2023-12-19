## Steps for deployment

1) Manual testing - the first thing to do is manually test all your commands for getting dependancies, getting the code and running it.
2) Script - write a script using those commands and test it on a fresh vm, and run it multiple times to make sure it is idempotent.
3) User data - When you are 100% happy with your script make a new vm and paste your script into the user data, making sure to check it worked correctly after it has loaded.
4) AMI - If your user data test workied you can create an AMI from your user data instance, then create a new instance from your AMI, remembering to add any navigation and run commands to the user data, and them make sure that works correctly once it has fully loaded up.