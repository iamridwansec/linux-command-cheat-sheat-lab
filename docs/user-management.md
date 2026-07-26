#Basic User Management Commands

> **Operating System:** Kali Linux 2026.x  
> **Shell:** Zsh  
> **Author:** Ridwan  
> **Purpose:** Practical documentation of basic Linux commands with screenshots and explanations.

This document contains the basic Linux commands executed during this lab.

# User Management

## Introduction

User management in Linux involves creating users, modifying accounts, locking passwords, assigning users to groups, and removing accounts when they are no longer needed. These tasks are common in system administration and security management.

---

## Table of Contents

- Lab 01 – Viewing User Information
- Lab 02 – Creating and Removing Users
- Lab 03 – Managing Groups

---

# Lab 01 – Viewing User Information

## Objective

Learn how to display information about the current user and other users on the system.

---

### Command 1: `whoami`

#### Description

The `whoami` command displays the username of the currently logged-in user.

#### Syntax

```bash
whoami
```

#### Expected Output

Displays your current username.

---

### Command 2: `finger`

#### Description

The `finger` command shows information about users currently logged in or available on the system.

#### Syntax

```bash
finger
```

#### Expected Output

Displays information about logged-in users.

> Note: `finger` may not be installed by default on some Linux systems.

---

### Command 3: `finger username`

#### Description

Displays information about a specific user.

#### Syntax

```bash
finger username
```

#### Expected Output

Shows details about the specified user account.

---

## Commands Executed

```bash
whoami
finger
finger username
```

---

## Screenshot

```
screenshots/users/lab-01-viewing-users.png
```

---

## Skills Gained

After completing this lab, I can:

- Display my current username.
- Check information about logged-in users.
- View information for a specific user.

---

## Conclusion

This lab introduced basic user information commands used for monitoring accounts and checking login activity.

---

# Lab 02 – Creating and Removing Users

## Objective

Learn how to create a new user, lock a password, and remove a user account.

---

### Command 1: `sudo adduser username`

#### Description

The `adduser` command creates a new user account.

#### Syntax

```bash
sudo adduser username
```

#### Example

```bash
sudo adduser testuser
```

#### Expected Output

Creates the user account and prompts you to set a password and user details.

---

### Command 2: `sudo passwd -l username`

#### Description

The `passwd -l` command locks a user’s password so the account cannot be used to log in with a password.

#### Syntax

```bash
sudo passwd -l username
```

#### Example

```bash
sudo passwd -l testuser
```

#### Expected Output

The user password is locked.

---

### Command 3: `sudo userdel -r username`

#### Description

The `userdel -r` command removes a user account and deletes the user’s home directory.

#### Syntax

```bash
sudo userdel -r username
```

#### Example

```bash
sudo userdel -r testuser
```

#### Expected Output

The user account and related files are removed.

> Important: Use a test account only.

---

## Commands Executed

```bash
sudo adduser testuser
sudo passwd -l testuser
sudo userdel -r testuser
```

---

## Screenshot

```
screenshots/users/lab-02-user-management.png
```

---

## Skills Gained

After completing this lab, I can:

- Create a new Linux user.
- Lock a user’s password.
- Remove a user account safely.
- Understand when administrative privileges are required.

---

## Conclusion

This lab demonstrated how to create, lock, and delete Linux user accounts. These actions are important for maintaining system security and managing access.

---

---

# Lab 03 – Managing Groups

## Objective

Learn how to create a test group, add a user to it, verify membership, and remove the user from the group.

---

### Command 1: `sudo groupadd labgroup`

#### Description

The `groupadd` command creates a new group. In this lab, we create a temporary group called `labgroup`.

#### Syntax

```bash
sudo groupadd labgroup
```

#### Expected Output

Creates a new group named `labgroup`.

---

### Command 2: `sudo adduser testuser`

#### Description

The `adduser` command creates a new test user account. This user will be added to the group.

#### Syntax

```bash
sudo adduser testuser
```

#### Expected Output

Creates the user account and home directory, then prompts for a password and user details.

> If `testuser` already exists, you can skip this step and use the existing test account.

---

### Command 3: `sudo usermod -a -G labgroup testuser`

#### Description

The `usermod -a -G` command adds a user to a supplementary group.

#### Syntax

```bash
sudo usermod -a -G labgroup testuser
```

#### Expected Output

Adds `testuser` to the `labgroup` group.

> Important: The `-a` option is required so the user is added without removing other group memberships.

---

### Command 4: `id testuser`

#### Description

The `id` command shows the user’s UID, primary group, and supplementary groups.

#### Syntax

```bash
id testuser
```

#### Expected Output

Displays information similar to this:

```text
uid=1001(testuser) gid=1001(testuser) groups=1001(testuser),27(sudo),1002(labgroup)
```

---

### Command 5: `sudo deluser testuser labgroup`

#### Description

The `deluser` command removes a user from a specific group.

#### Syntax

```bash
sudo deluser testuser labgroup
```

#### Expected Output

Removes `testuser` from the `labgroup` group.

---

## Commands Executed

```bash
sudo groupadd labgroup
sudo adduser testuser
sudo usermod -a -G labgroup testuser
id testuser
sudo deluser testuser labgroup
```

---

## Screenshot

```
screenshots/users/lab-03-group-management.png
```

---

## Skills Gained

After completing this lab, I can:

- Create a Linux group.
- Create a test user account.
- Add a user to a supplementary group.
- Verify group membership.
- Remove a user from a group.

---

## Conclusion

This lab demonstrated group management in Linux using a practical example. I learned how to create a temporary group, add a user to it, verify the change, and remove the user from the group afterward.
