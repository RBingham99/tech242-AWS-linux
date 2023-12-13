## Enviroment variables

Enviroment variables can be seen by entering the command `printenv`, which will show all of your enviroment variables or you can use `printenv` followed by the name of the variable you want and it will only print that variable.

You can create a variable by typing `NAMEOFVARIABLE=valueOfVariable`, but with whatever you want your variable to be called and whatever value you want it to hold. It is good practice to make all variables block capitals with no spaces. You can also create variables like this in scripts.

You can see that variable by entering `echo $NAMEOFVARIABLE`, however it is just a normal variable at the moment, not an enviroment variable. 

To create an enviroment variable you can do what we did before but you will need to put `export` before the name of the variable.

If you want to make your variable persistant, so that it still exists when you disconnect and reconnect or restart your machine, you will need to put your enviroment variable in your `.bashrc`. To do this you need to go to your home directory by using the command `cd ~`, then do `nano .bashrc` to open your `.bashrc` file, then on the last line of the file add your enviroment variable. 

Your enviroment variable will now exist when you start your machine however it will not already exist, you will first need to use the `source` command to re-run your `.bashrc` file.