## Managing file ownership and permissions

You can only change the permissions and ownership for a file or directory if you're its owner or you're logged in as root. 
To change the owner of a file the command is `chown` followed by the name of the ner owner, then a `:`, then the group name and finally the file name.

The group refers to a group of users, like admins for example if you want them to have different permissions to everyone else without needing to be the owner.

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

Or you could use `chmod +r`, `chmod +w` or `chmod +x` followed by the file/folder to give read, write or execute permissions. However this command will effect the owner, group and everyone else.

When you do `ls -l` you will see all files and folders in your current directory and their permissions will look something like this:
`drwxrwxrwx` 

The `d` at the begining means it's a directory, the `rwx` after the `d` is the read, write and execute permissions for the owner, the next set of `rwx` are for groups and the last set is for others/everyone. So for this example it is a directory and everyone has full permissions. If the user only had read and write permissions, but not execute permissions, the first `rwx` would look like `rw-`.