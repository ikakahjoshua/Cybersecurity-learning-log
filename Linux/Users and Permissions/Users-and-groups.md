# Linux Users and Groups

## Objective

Understand how Linux manages user accounts and groups, how user identities are represented through UIDs and GIDs, and how account information is stored and managed.

## 1. Understanding Linux Users

Linux is a multi-user operating system. This means multiple users can access the same system while maintaining separate identities and permissions.

Each user account has a unique User ID (UID), which the system uses internally to identify users.

There are different categories of user accounts:

- **Root account:** The superuser account with unrestricted administrative privileges.
- **Regular users:** Accounts created for normal system usage.
- **System users:** Accounts used by services and background processes.

## 2. Understanding Groups

A group is a collection of users that share common access permission
Every user has a primary group and may belong to additional supplementary groups.

## 3. Inspecting User Information

Commands used:

- `whoami` — Displays the current username.
- `id` — Displays the current UID, primary GID, and supplementary groups.
- `who` — Displays currently logged-in users.
- `groups` — Displays the groups associated with the current user.
- `getent passwd` — Retrieves user account information.
- `getent group` — Retrieves group information.

## 4. Important Account Files

Linux stores user and group information in several system files.

### /etc/passwd

Contains user account information, including:

- Username
- Password placeholder
- UID
- GID
- User information
- Home directory
- Login shell

### /etc/shadow

Stores password-related information, including password hashes.

Access to this file is restricted because it contains sensitive authentication information.

### /etc/group

Contains information about groups, including group names, GIDs, and supplementary group members.

## 5. User Management

Commands used:

- `useradd` — Creates a user account.
- `adduser` — Provides an interactive method of creating users on supported distributions.
- `usermod` — Modifies an existing user account.
- `passwd` — Changes a user's password.
- `userdel` — Removes a user account.

## 6. Group Management

Commands used:

- `groupadd` — Creates a group.
- `groupmod` — Modifies a group.
- `groupdel` — Removes a group.
- `gpasswd` — Administers group membership and passwords.
- `usermod -aG` — Adds a user to supplementary groups.

## Screenshots

Screenshots of relevant commands and their outputs will be stored in the `Images/` directory.

## Conclusion

Linux uses users and groups to identify processes and manage access to system resources.

Understanding account management provides the foundation for understanding Linux authentication, authorization, and file permission systems.
