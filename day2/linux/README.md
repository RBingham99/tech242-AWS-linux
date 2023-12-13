## Linux

# Important points
- `/` is root directory path from root directory, so starting with / is called an absolute path.
- `~ `is home directory.

# Linux commands
- `uname` checks OS.
- `--help` can be run after most commands to se possible flags.
- `whoami` shows current user.
- `cat /etc/shells` shows installed shells.
- `history` show previous commands.
- `!<num>` after history will run command with that number.
- `ls` show list, `ls -l` long version, `ls -a` show all including hidden files (can do `-la` to combine l and a).
- `mv` can move a file or can rename a file.
- `curl` followed by a url downloads from that url.
- `cp` copy.
- `rm` remove file.
- `mkdir` make directory.
- `rmdir` remove directory or `rm -r` (-r removes directory and recursively removes everything inside).
- `touch` make empty file.
- `cat` print file contents.
- `nano` edit file.
- `head<num>` print num of lines from top.
- `tail<num>` print num of lines from bottom.
- `nl` number lines.
- `grep` search for string, can be used like `cat <filename.txt> | grep <string to look for>`.
- `sudo` means superuser do.
- `apt` is the package list.
- `sudo su` temporarily logs you in as root user.
- `cd` on its own moves you to the home directory or if followed by a path (either from your current directory or your root directory if the path starts with `/`) will take you to the end of that path.
- `systemctl` manages system processes, ususlly has `sudo` before it and is then followed by what you want to do, eg: `status`, `restart`, `start`, `stop`, ect, and then followed by the proccess we would like to do that on, `nginx` for example.
- `enable` can be used with `systemctl` in place of `status`, `restart`, ect to make the proccess always run on start-up.
- `clear` will clear the terminal
- `sleep` will put your terminal to sleep for a given amount of time, or if you put `&` at the end it will run in the background
- `kill` kill followed by a PID will kill a process but make sure you only kill processes that you know exactly what they are doing, to avoid breaking anything. You can also put `-9` after kill to make it a brutal kill, which is the strongest kill but that makes it the most dangerous. Killing a parent process can create a zombie process.
