# Basic Linux Commands

> **Operating System:** Kali Linux 2026.x  
> **Shell:** Bash  
> **Author:** Ridwan  
> **Purpose:** Practical documentation of basic Linux commands with screenshots and explanations.

This document contains the basic Linux commands executed during this lab.

# File Permissions

## Introduction

Linux uses a permission system to control who can read, write, or execute files and directories. Every file has an owner, a group, and permission settings that help secure the system from unauthorized access.

---

## Table of Contents

- Lab 01 – Understanding Linux Permissions
- Lab 02 – Changing File Permissions
- Lab 03 – Changing File Ownership

---

# Lab 01 – Understanding Linux Permissions

## Objective

Learn how to view file permissions and understand the meaning of read, write, and execute permissions.

---

### Command 1: `ls -l`

#### Description

The `ls -l` command displays files and directories in a detailed format, including permissions, owner, group, file size, and last modification date.

#### Syntax

```bash
ls -l
```

#### Expected Output

Displays information similar to:

```text
-rw-r--r-- 1 cypher cypher 256 Jul 25 notes.txt
```

---

### Understanding Permission Numbers

Linux permissions are represented using numbers.

| Number | Permission | Symbol |
|---------|------------|--------|
| 4 | Read | r |
| 2 | Write | w |
| 1 | Execute | x |

Permission numbers are calculated by adding these values together.

Examples:

| Number | Permission |
|---------|------------|
| 7 | rwx |
| 6 | rw- |
| 5 | r-x |
| 4 | r-- |

---

## Commands Executed

```bash
ls -l
```

---

## Screenshot

```
screenshots/permissions/lab-01-view-permissions.png
```

---

## Skills Gained

After completing this lab, I can:

- View Linux file permissions.
- Identify file owners and groups.
- Understand numeric permission values.
- Interpret permission symbols.

---

## Conclusion

This lab introduced the Linux permission model and demonstrated how permission values control access to files and directories.

---

# Lab 02 – Changing File Permissions

## Objective

Learn how to modify file and directory permissions using the `chmod` command.

---

### Command 1: `chmod 775 file`

#### Description

The `chmod` (Change Mode) command changes the permissions of a file or directory. In this example, the permission value **775** grants:

- **Owner:** Read, Write, Execute (7)
- **Group:** Read, Write, Execute (7)
- **Others:** Read, Execute (5)

#### Syntax

```bash
chmod 775 file
```

#### Example

```bash
touch testfile.txt
chmod 775 testfile.txt
ls -l testfile.txt
```

#### Expected Output

The file permissions change to:

```text
-rwxrwxr-x
```

---

### Command 2: `chmod -R 600 folder`

#### Description

The `-R` option applies permission changes recursively to a directory and all of its contents.

The permission value **600** grants:

- **Owner:** Read, Write (6)
- **Group:** No permissions (0)
- **Others:** No permissions (0)

#### Syntax

```bash
chmod -R 600 folder
```

#### Example

```bash
mkdir DemoFolder
touch DemoFolder/file1.txt
chmod -R 600 DemoFolder
ls -l DemoFolder
```

#### Expected Output

All files inside the directory receive permissions similar to:

```text
-rw-------
```

---

## Commands Executed

```bash
touch testfile.txt
chmod 775 testfile.txt
ls -l testfile.txt

mkdir DemoFolder
touch DemoFolder/file1.txt
chmod -R 600 DemoFolder
ls -l DemoFolder
```

---

## Screenshot

```
screenshots/permissions/lab-02-changing-permissions.png
```

---

## Skills Gained

After completing this lab, I can:

- Change file permissions using `chmod`.
- Understand the meaning of permission value `775`.
- Apply permissions recursively using the `-R` option.
- Verify permission changes using `ls -l`.

---

## Conclusion

This lab demonstrated how to modify Linux file and directory permissions using the `chmod` command. I learned how numeric permission values control access rights and how to apply permission changes recursively to an entire directory.

---

# Lab 03 – Changing File Ownership

## Objective

Learn how to change the ownership of files and directories using the `chown` command.

---

### Command 1: `chown user:group file`

#### Description

The `chown` (Change Owner) command changes the ownership of a file or directory. It allows you to assign a new owner and group to the specified file.

> **Note:** This command usually requires **sudo** privileges because changing file ownership is an administrative task.

---

#### Syntax

```bash
chown user:group file
```

---

#### Example

```bash
touch ownership.txt
ls -l ownership.txt

sudo chown cypher:cypher ownership.txt

ls -l ownership.txt
```

> Replace `cypher` with your actual Linux username if it is different.

---

#### Expected Output

Before changing ownership:

```text
-rw-r--r-- 1 olduser oldgroup 0 Jul 26 ownership.txt
```

After changing ownership:

```text
-rw-r--r-- 1 cypher cypher 0 Jul 26 ownership.txt
```

---

## Commands Executed

```bash
touch ownership.txt
ls -l ownership.txt
sudo chown cypher:cypher ownership.txt
ls -l ownership.txt
```

---

## Screenshot

```
screenshots/permissions/lab-03-changing-ownership.png
```

---

## Skills Gained

After completing this lab, I can:

- View file ownership.
- Change the owner of a file.
- Change the group assigned to a file.
- Verify ownership changes using `ls -l`.

---

## Conclusion

This lab introduced the `chown` command, which is used to change file ownership in Linux. Proper ownership management is essential for maintaining security, controlling access to files, and administering multi-user Linux systems.
