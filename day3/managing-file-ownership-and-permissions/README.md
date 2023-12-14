## Managing file ownership and permissions

# Ownership
You can only change the permissions and ownership for a file or directory if you're its owner or you're logged in as root. 
To change the owner of a file the command is `chown` followed by the name of the new owner, then a `:`, then the group name and finally the file name.

# Groups
The group refers to a group of users, like admins for example if you want them to have different permissions to everyone else without needing to be the owner.
To see all your groups you can use the command `cat /etc/group`.
To create a group you can use the command `sudo groupadd` followed by the name of the group.
To add a user to a group you can use the command `sudo usermod -aG` followed by the name of the group, then the name of the user.
To remove a user from a group you can use the command `sudo gpasswd -d` followed by the name of the user, then the name of the group.
To delete a group you can use the command `sudo groupdel` followed by the name of the group.

# Changing permissions
To change permisions on a file or folder you use the `chmod` command followed by 3 numbers, the first for the owner, the second for the group and the third for everyone else, the numbers can be:

- 0 – no access to the file whatsoever
- 1 – execute permissions only
- 2 – write permissions only
- 3 – write and execute permissions
- 4 – read permissions only
- 5 – read and execute permissions
- 6 – read and write permissions
- 7 – read, write and execute permissions (full permissions)

Followed by the file/folder you want to change the permissions on.

Or you could use `chmod +r`, `chmod +w` or `chmod +x` followed by the file/folder to add read, write or execute permissions, you can also swap the `+` for a `-` to remove those permissions. However this command will effect the owner, group and everyone else. If you only want to change the user permissions you can do `chmod u+r`, or replace the `r` with w or x depending which permission you want to change, similarly you can replace the `u` with a `g` or `o` to change just the grouppermissions or other permissions.

When you do `ls -l` you will see all files and folders in your current directory and their permissions will look something like this:
`drwxrwxrwx` 

The `d` at the begining means it's a directory, the `rwx` after the `d` is the read, write and execute permissions for the owner, the next set of `rwx` are for groups and the last set is for others/everyone. So for this example it is a directory and everyone has full permissions. If the user only had read and write permissions, but not execute permissions, the first `rwx` would look like `rw-`.