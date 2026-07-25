# Basic Linux Commands

> **Operating System:** Kali Linux 2026.x  
> **Shell:** Bash  
> **Author:** Ridwan  
> **Purpose:** Practical documentation of basic Linux commands with screenshots and explanations.

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



---

# Lab 03 – File Creation and Viewing

## Objective

Learn how to create a file using the `cat` command and display its contents from the terminal.

---

### Command 1: `cat > notes.txt`

#### Description

The `cat > filename` command creates a new file and allows you to enter text directly from the terminal. Press **Ctrl + D** when you are finished typing to save the file.

#### Syntax

```bash
cat > notes.txt
```

#### Expected Output

A new file named `notes.txt` is created with the text you entered.

---

### Command 2: `cat notes.txt`

#### Description

The `cat` command displays the contents of a file in the terminal.

#### Syntax

```bash
cat notes.txt
```

#### Expected Output

Displays all the text stored inside `notes.txt`.

---

### Command 3: `cat notes.txt notes.txt > merged.txt`

#### Description

Combines the contents of two files and writes the output to a new file. In this lab, the same file is used twice for demonstration purposes.

#### Syntax

```bash
cat notes.txt notes.txt > merged.txt
```

#### Expected Output

Creates a new file named `merged.txt` containing the combined contents.

---

### Command 4: `cat merged.txt`

#### Description

Displays the contents of the newly created merged file.

#### Syntax

```bash
cat merged.txt
```

#### Expected Output

Shows the combined contents stored in `merged.txt`.

---

## Commands Executed

```bash
cat > notes.txt
cat notes.txt
cat notes.txt notes.txt > merged.txt
cat merged.txt
```

---

## Screenshot

```
screenshots/basic/lab-03-file-creation-viewing.png
```

---

## Skills Gained

After completing this lab, I can:

- Create a text file using the terminal.
- View file contents using the `cat` command.
- Merge file contents into another file.
- Verify the contents of a newly created file.

---

## Conclusion

This lab introduced the `cat` command for creating, viewing, and combining text files. These are fundamental file-handling operations in Linux.


---

# Lab 04 – Moving, Renaming and Deleting Files

## Objective

Learn how to move, rename, and delete files using basic Linux commands. This lab also introduces the `sudo` command for executing commands with elevated privileges.

---

### Command 1: `mv notes.txt mynotes.txt`

#### Description

The `mv` (move) command renames a file when the source and destination are in the same directory.

#### Syntax

```bash
mv notes.txt mynotes.txt
```

#### Expected Output

The file `notes.txt` is renamed to `mynotes.txt`.

---

### Command 2: `mv mynotes.txt LinuxLab/`

#### Description

The `mv` command can also move a file from one directory to another.

#### Syntax

```bash
mv mynotes.txt LinuxLab/
```

#### Expected Output

The file `mynotes.txt` is moved into the `LinuxLab` directory.

---

### Command 3: `sudo`

#### Description

The `sudo` (SuperUser DO) command allows an authorized user to execute commands with administrative or root privileges.

#### Syntax

```bash
sudo command
```

#### Example

```bash
sudo ls /root
```

#### Expected Output

Executes the specified command with elevated privileges. You may be prompted to enter your password.

---

### Command 4: `rm merged.txt`

#### Description

The `rm` (remove) command permanently deletes a file from the filesystem.

#### Syntax

```bash
rm merged.txt
```

#### Expected Output

The file `merged.txt` is removed from the current directory.

---

## Commands Executed

```bash
mv notes.txt mynotes.txt
mv mynotes.txt LinuxLab/
sudo ls /root
rm merged.txt
```

---

## Screenshot

```
screenshots/basic/lab-04-moving-renaming-deleting.png
```

---

## Skills Gained

After completing this lab, I can:

- Rename files using the `mv` command.
- Move files between directories.
- Execute commands with administrative privileges using `sudo`.
- Permanently delete files using the `rm` command.

---

## Conclusion

This lab demonstrated essential file management tasks in Linux, including renaming, moving, deleting files, and using administrative privileges when required.



---

# Lab 05 – Help, History and Directory Management

## Objective

Learn how to access Linux command documentation, review previously executed commands, clear the terminal screen, and remove empty directories.

---

### Command 1: `man ls`

#### Description

The `man` (manual) command displays the official documentation for Linux commands. In this lab, it opens the manual page for the `ls` command.

#### Syntax

```bash
man ls
```

#### Expected Output

Displays the manual page for the `ls` command. Press **q** to exit the manual.

---

### Command 2: `history`

#### Description

The `history` command displays a numbered list of previously executed commands in the current shell session.

#### Syntax

```bash
history
```

#### Expected Output

Shows a list of commands that have been executed in the terminal.

---

### Command 3: `clear`

#### Description

The `clear` command clears all visible output from the terminal screen, providing a clean workspace.

#### Syntax

```bash
clear
```

#### Expected Output

The terminal screen is cleared while the current session remains active.

---

### Command 4: `rmdir LinuxLab`

#### Description

The `rmdir` (remove directory) command deletes an empty directory.

> **Note:** The directory must be empty before it can be removed. If it contains files, Linux will display an error.

#### Syntax

```bash
rmdir LinuxLab
```

#### Expected Output

The empty `LinuxLab` directory is removed successfully.

---

## Commands Executed

```bash
man ls
history
clear
rmdir LinuxLab
```

---

## Screenshot

```
screenshots/basic/lab-05-help-history-directory.png
```

---

## Skills Gained

After completing this lab, I can:

- Access Linux manual pages using the `man` command.
- Review previously executed commands with `history`.
- Clear the terminal screen using `clear`.
- Remove empty directories using `rmdir`.

---

## Conclusion

This lab introduced essential utility commands that improve productivity in the Linux terminal. I learned how to access command documentation, review command history, maintain a clean terminal workspace, and safely remove empty directories.

---

# Lab 06 – File Printing and Formatting

## Objective

Learn how to format file output for printing by adding line numbers, headers, and multiple columns.

---

### Command 1: `pr -n notes.txt`

#### Description

The `pr` command formats a file for printing. The `-n` option displays line numbers beside each line.

#### Syntax

```bash
pr -n notes.txt
```

#### Expected Output

Displays the contents of `notes.txt` with line numbers.

---

### Command 2: `pr -h "Linux Lab" notes.txt`

#### Description

The `-h` option adds a custom header to the formatted output.

#### Syntax

```bash
pr -h "Linux Lab" notes.txt
```

#### Expected Output

Displays the file with the header **Linux Lab** at the top.

---

### Command 3: `pr -2 notes.txt`

#### Description

The `-2` option formats the file into two columns.

#### Syntax

```bash
pr -2 notes.txt
```

#### Expected Output

Displays the contents of the file in two columns.

---

## Commands Executed

```bash
pr -n notes.txt
pr -h "Linux Lab" notes.txt
pr -2 notes.txt
```

---

## Screenshot

```
screenshots/basic/lab-06-print-formatting.png
```

---

## Skills Gained

After completing this lab, I can:

- Display line numbers in a file.
- Add custom headers to formatted output.
- Format file contents into multiple columns.

---

## Conclusion

This lab introduced the `pr` command, which is commonly used to prepare text files for printing or improved readability.


---

# Lab 07 – Package Management

## Objective

Learn how to update package information and install software using the APT package manager.

---

### Command 1: `sudo apt update`

#### Description

Downloads the latest package information from configured software repositories.

#### Syntax

```bash
sudo apt update
```

#### Expected Output

The package lists are updated successfully.

---

### Command 2: `sudo apt install tree`

#### Description

Installs the **tree** package, which displays directory structures in a tree-like format.

#### Syntax

```bash
sudo apt install tree
```

#### Expected Output

The `tree` package is installed if it is not already present.

---

### Command 3: `tree`

#### Description

Displays the current directory structure in a hierarchical tree format.

#### Syntax

```bash
tree
```

#### Expected Output

Shows folders and files in a tree-like structure.

---

## Commands Executed

```bash
sudo apt update
sudo apt install tree
tree
```

---

## Screenshot

```
screenshots/basic/lab-07-package-management.png
```

---

## Skills Gained

After completing this lab, I can:

- Update package information.
- Install software using APT.
- Display directory structures using the `tree` command.

---

## Conclusion

This lab introduced basic package management in Linux and demonstrated how to install and verify command-line utilities.
