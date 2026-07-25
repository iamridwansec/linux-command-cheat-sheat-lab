# Basic Linux Commands

This document contains the basic Linux commands executed during this lab.

---

# Lab 1 – Navigation Commands

## Commands

- pwd
- ls
- ls -a
- ls -al
- cd ~
- cd ..
- cd /

---

## 1. pwd

### Description

Displays the current working directory.

### Syntax

```bash
pwd
```

### Practical Use

Shows your current location in the Linux filesystem.

---

## 2. ls

### Description

Lists files and directories.

### Syntax

```bash
ls
```

### Practical Use

Displays the contents of the current directory.

---

## 3. ls -a

### Description

Displays all files including hidden files.

### Syntax

```bash
ls -a
```

### Practical Use

Useful for viewing hidden configuration files.

---

## 4. ls -al

### Description

Displays detailed information about files.

### Syntax

```bash
ls -al
```

### Practical Use

Shows permissions, owner, size and modification date.

---

## 5. cd ~

### Description

Changes to the home directory.

### Syntax

```bash
cd ~
```

### Practical Use

Quickly returns to your home directory.

---

## 6. cd ..

### Description

Moves up one directory.

### Syntax

```bash
cd ..
```

### Practical Use

Navigate to the parent directory.

---

## 7. cd /

### Description

Changes to the root directory.

### Syntax

```bash
cd /
```

### Practical Use

Access the root of the Linux filesystem.

---

## Screenshot

**File:**

```
screenshots/basic/lab-01-navigation.png
```

---

# Lab 02 – Directory Management

## Objective

Learn how to create directories, navigate into them, and return to the parent directory.

---

### Command 1: `mkdir LinuxLab`

#### Description

The `mkdir` (Make Directory) command creates a new directory with the specified name.

#### Syntax

```bash
mkdir LinuxLab
```

#### Expected Output

A new directory named **LinuxLab** is created in the current working directory.

---

### Command 2: `cd LinuxLab`

#### Description

The `cd` (Change Directory) command moves the current working directory into the specified directory.

#### Syntax

```bash
cd LinuxLab
```

#### Expected Output

The terminal changes the current working directory to **LinuxLab**.

---

### Command 3: `pwd`

#### Description

Displays the absolute path of the current working directory to confirm that you are inside the newly created directory.

#### Syntax

```bash
pwd
```

#### Expected Output

Displays the full path ending with **LinuxLab**.

---

### Command 4: `cd ..`

#### Description

The `cd ..` command moves one directory level up to the parent directory.

#### Syntax

```bash
cd ..
```

#### Expected Output

Returns to the parent directory.

---

### Command 5: `ls`

#### Description

Lists the files and directories in the current directory after returning to the parent directory.

#### Syntax

```bash
ls
```

#### Expected Output

Displays the contents of the parent directory, including the **LinuxLab** directory.

---

## Commands Executed

```bash
mkdir LinuxLab
cd LinuxLab
pwd
cd ..
ls
```

---

## Screenshot

```
screenshots/basic/lab-02-directory-management.png
```

---

## Conclusion

In this lab, I learned how to create a new directory, navigate into it, verify my location using `pwd`, return to the parent directory, and list its contents.
