# chmod, chown, chgrp and umask

## Objective

Understand how Linux permissions and ownership are modified, how numeric and symbolic permission modes work, and how umask influences default permissions.

## 1. Understanding chmod

The `chmod` command changes file and directory permissions.

There are two main ways to specify permissions:

- Symbolic mode.
- Numericbmode.

### Symbolic Mode

Symbolic permissions use letters to represent ownership categories and permission types.

Ownership categories:

- `u` = User/owner.
- `g` = Group.
- `o` = Others.
- `a` = All.

Permission operators:

- `+` = Add permission.
- `-` = Remove permission.
- `=` = Set exact permission.

Examples:

`chmod u+x file.sh`

Adds execute permission for the owner.

`chmod g-w file.txt`

Removes write permission from the group.

`chmod o+r file.txt`

Adds read permission for others.

`chmod a-x file.sh`

Removes execute permission from everyone.

### Numeric Mode

Linux represents permissions using three numeric values:

| Permission | Value |
|---|---|
| Read (r) | 4 |
| Write (w) | 2 |
| Execute (x) | 1 |

The values are added together to produce the permission number.

Examples:

- `7` = Read + Write + Execute.
- `6` = Read + Write.
- `5` = Read + Execute.
- `4` = Read only.
- `0` = No permissions.

Example:

`chmod 755 file.sh`

Results in:

- Owner: Read, write, execute.
- Group: Read, execute.
- Others: Read, execute.

`chmod 644 file.txt`

Results in:

- Owner: Read and write.
- Group: Read only.
- Others: Read only.

## 2. Understanding chown

The `chown` command changes the owner of a file or directory.

Examples:

`sudo chown joshua file.txt`

Changes the owner to joshua.

`sudo chown joshua:developers file.txt`

Changes both the owner and group.

Recursive ownership changes:

`sudo chown -R joshua:developers directory/`

Applies ownership changes to a directory and its contents.

## 3. Understanding chgrp

The `chgrp` command changes the group ownership of files and directories.

Example:

`sudo chgrp developers file.txt`

Changes the file's group to developers.

## 4. Understanding umask

The `umask` command controls which permissions are removed from the default permissions assigned to newly created files and directories.

Linux commonly uses these initial permission values:

- Files: 666.
- Directories: 777.

The umask removes permissions from these initial values.

Example:

`umask 022`

For a newly created file:

666 - 022 = 644

For a newly created directory:

777 - 022 = 755

This produces:

- Files: `rw-r--r--`
- Directories: `rwxr-xr-x`

Note: This is a simplified calculation for the standard permission bits. The result also depends on the application creating the file and the filesystem environment.

Useful commands:

`umask`

Displays the current umask.

`umask -S`

Displays the current umask symbolically.

`umask 027`

Sets the umask to 027 for the current shell.

## Screenshots

Screenshots of relevant commands and their outputs will be stored in the `Images/` directory.

## Conclusion

The chmod, chown, chgrp, and umask commands provide important mechanisms for managing Linux permissions and ownership.

Understanding how they work helps prevent unauthorized access and improves overall system security.
