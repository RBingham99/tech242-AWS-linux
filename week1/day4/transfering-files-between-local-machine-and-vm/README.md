## Transfering files betwen local machine and VM

# To transfer a file from your local machine to your VM 
1) First you need to open 2 seperate terminals, 1 that is ssh'ed into your VM and one that is running git bash on your local machine.
2) Now in your git bash termianal on your local machine use the command:
`scp -i ~/path/to/your/pem/file ~/path/to/the/local/file/you/want/on/your/vm remote_username@publicIpOfYourVM:~/path/to/directory/on/your/vm/that/you/want/your/file/copied/to`.

# To transfer a directory from your local machine to your VM 
1) First you need to open 2 seperate terminals, 1 that is ssh'ed into your VM and one that is running git bash on your local machine.
2) Now in your git bash termianal on your local machine use the command:
`scp -r -i ~/path/to/your/pem/file ~/path/to/the/local/directory/you/want/on/your/vm remote_username@publicIpOfYourVM:~/path/to/directory/on/your/vm/that/you/want/your/directory/copied/to`.<br>
The only real difference between transfering a file or a directory is the -r at the begining for directories.