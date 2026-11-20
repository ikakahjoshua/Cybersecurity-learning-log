# Linux File Permissions and Ownership

## Objective

Understand how Linux controls access to files and directories through ownership and permission systems.

## 1. Understanding File Ownership

Every file and directory in Linux has an associated owner and group.

Linux uses three ownership categories:

- **User (u):** The owner of the file or directory.
- **Group (g):** The group associated with the file or directory.
- **Others (o):** All users who are neither the owner nor members of the associated group.

## 2. Understanding Permission Types

Linux uses three basic permission types:

| Permission | Symbol | Meaning |
|---|---|---|
| Read | r | View file contents or list directory contents |
| Write | w | Modify files or create/delete directory entries |
| Execute | x | Execute files or access directories |

Directory permissions behave differently from file permissions.

For example:

- Read permission allows listing directory contents.
- Write permission allows creating, deleting, or renaming entries.
- Execute permission allows accessing entries inside the directory.

## 3. Reading Permission Strings

Command:

`ls -l`

Example output:

`-rwxr-xr-- 1 joshua developers 1024 Nov 20 example.sh`

The permission string can be divided into four parts:

- First character: File type.
- Next three characters: Owner permissions.
- Next three characters: Group permissions.
- Last three characters: Others permissions.

Example:

`-rwxr-xr--`

- `-` = Regular file.
- `rwx` = Owner can read, write, and execute.
- `r-x` = Group can read and execute.
- `r--` = Others can only read.

## 4. Changing File Ownership

Commands used:

- `chown` — Changes file or directory ownership.
- `chgrp` — Changes the group ownership.

Examples:

`sudo chown joshua file.txt`

`sudo chown joshua:developers file.txt`

`sudo chgrp developers file.txt`

## 5. Special Linux Permissions

Linux provides three special permission mechanisms.

### SUID (Set User ID)

SUID allows an executable program to run with the effective privileges of its file owner.

It is represented by `s` in the owner's execute position.

Example:

`-rwsr-xr-x'


### SGID (Set Group ID)

On executable files, SGID allows a program to run with the effective group identity of the file's group.

On directories, newly created files and directories inherit the directory's group ownership.

It is represented by `s` in the group's execute position.

Example:

`-rwxr-sr-x`

### Sticky Bit

The sticky bit is commonly used on shared directories.

It restricts file deletion and renaming so that users generally cannot delete or rename files belonging to other users.

Example:

`drwxrwxrwt`

The `/tmp` directory commonly uses the sticky bit.

## 6. Inspecting Permissions

Commands used:

- `ls -l` — Displays file permissions and ownership.
- `stat` — Displays detailed file information.
- `namei -l` — Displays permissions along a pathname.
- `getfacl` — Displays access control lists where supported.

Pay attention to the differences between file permissions and directory permissions.

## Screenshots

Screenshots of relevant commands and their outputs will be stored in the `Images/` directory.

## Conclusion

Linux file permissions and ownership provide a fundamental access-control mechanism.

Understanding these mechanisms is essential for managing system security and identifying permission-related vulnerabilities.
