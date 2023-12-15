## User data

With user data we can make a script run the first time your VM starts.

User data will run as root user so sudo isn't necassery but it won't hurt anything.

User data will run in your root directory `/` so you need to check your paths when navigating in your script.

To add user data simply go right to the bottom of the screen when you are creating an instance and click the "advanced details" dropdown.<br>
![Advanced-details-dropdown](../../readme-images/advanced-details-dropdown.png)

Then scrool down to the bottom of the dropdown and paste your script into the "User data" textbox.<br>
![textbox-for-user-data](../../readme-images/textbox-for-user-data.png)

Now when you launch your instance, the script will run, but it will take a little while so be patient.