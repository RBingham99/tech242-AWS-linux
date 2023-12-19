## Scripts

# In script files:
- `#!` is called a shabang, it should go on the first line of your script followed by the path to the shell you want to read the script, we used bash so wrote `#!/bin/bash`.
- `#` means everything after it on the same line is a comment.
-  Write commands like we do in terminal.
- It's best practice to `echo` out small coments so when the scripts run it is easier to see what happend when.

# Proccess for creating a script

1) Create the script file by using the command `nano` followed by the name of the file, making sure to end it with `.sh`.
2) This will open up the file, on the first line put `#!` followed by the path to the shell you want to read the file, so `/bin/bash` to use bash.
3) Then plan your script, a good way to do that is using comments in the file, but you can do it however you like.
4) Next press `control + s` to save the file and `control + x` to exit the file.
5) Now manualy test all of the commands you want to use in the terminal, to make sure they work.
6) If they all work you can reopen your script file using the `nano` command and put the commands in the file.
7) It is a good idea to put `echo` statements before each command to say which command is about to run and after each command to say when it has finished, you may also want to add blank lines to make the output more readable when the script runs.
8) You can now use `control + s` to save the file and `control + x` to exit the file, and then run the script by entering `./` followed by the file name.
9) Your script will now run!

# Sidenotes
- The extention for a bash script is `.sh`.
- You should always test the commands in the terminal to make sure they work before writing a script.
- To run a script do `./` followed by the path to your script file so if you are in the same file just put the filename after the `./`.
- You should always try to make your scripts idempotent, which means they can run on any machine whether it is a clean, brand new machine or not, and still do the same thing.
- You can put `-y` after a command to stop it asking for user interaction.
- If a command you run with `-y` still requires some user interaction you can use `DEBIAN_FRONTEND=noninteractive` immedietly after `sudo` in your command to make sure it doesn't require user interaction, however this only works for debian OS's, like ubuntu.