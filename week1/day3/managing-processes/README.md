## Managing processes

# 2 types of processes
- System processes
- User processes

# Viewing processes
There are multiple ways to view processes, you can:
- You can use `ps` to view user processes.
- You can use `ps -A` or `ps -e` to view all processes.
- You can do `ps aux` to view all processes with extra detail.
- You can use `top` to show the processes using the most cpu power by default, but you can press `shift + m` to change to the processes using the most memory.

# When you view processes 
- You will see the PID for each process, the PID is the process ID.
- You will see the TTY for each process, the TTY relates to the terminal that the process is related to.

# Killing processes
- The `kill` command, followed by a PID will kill a process. 
- When killing a process make sure you only kill processes that you know exactly what they are doing, to avoid breaking anything.
- You can also put `-9` after kill to make it a brutal kill, which is the strongest kill but that makes it the most dangerous. 
- Killing a parent process can create a zombie process, which is a child process running without its parent, so should be killed as well.
- If you kill a process and it pops back up, it probably has a parent process restarting it so you will need to kill the parent first.