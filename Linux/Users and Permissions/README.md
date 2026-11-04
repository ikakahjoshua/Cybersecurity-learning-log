# Linux Users and Permissions

A practical learning log covering how Linux identifies users and groups,
stores account information, controls access to files and directories,
and applies default and special permissions.


### Approach 
Learn the concept, test it in a controlled environment,
record the result, and explain what happened.

## Learning Objectives

By the end of this section, I should be able to:

-   Explain the difference between users, groups, and system accounts.
-   Inspect the current user, UID, GID, and group memberships.
-   Create, modify, inspect, and remove users and groups safely.
-   Explain the purpose of `/etc/passwd`, `/etc/shadow`, and
    `/etc/group`.
-   Read Linux permission strings and identify owner, group, and others.
-   Change permissions and ownership using `chmod`, `chown`, and
    `chgrp`.
-   Explain SUID, SGID, and the sticky bit, including their security
    implications.
-   Explain how `umask` affects the permissions of newly created files
    and directories.
-   Troubleshoot common permission and account-management problems.
  
