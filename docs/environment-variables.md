# Basic Linux Commands

> **Operating System:** Kali Linux 2026.x  
> **Shell:** Bash  
> **Author:** Ridwan  
> **Purpose:** Practical documentation of basic Linux commands with screenshots and explanations.

This document contains the basic Linux commands executed during this lab.



# Environment Variables

## Introduction

Environment variables are dynamic values stored by the operating system that applications and the shell use during execution. They provide information about the current user, system configuration, and executable search paths.

---

## Table of Contents

- Lab 01 – Viewing Environment Variables
- Lab 02 – Creating Environment Variables

---

# Lab 01 – Viewing Environment Variables

## Objective

Learn how to view existing environment variables and understand their purpose in Linux.

---

### Command 1: `env`

#### Description

The `env` command displays all environment variables currently available in the shell session.

#### Syntax

```bash
env
```

#### Expected Output

Displays a list of environment variables and their values.

---

### Command 2: `echo $HOME`

#### Description

Displays the path to the current user's home directory.

#### Syntax

```bash
echo $HOME
```

#### Expected Output

Shows the absolute path of the user's home directory.

---

### Command 3: `echo $PATH`

#### Description

Displays the directories that Linux searches when you execute a command.

#### Syntax

```bash
echo $PATH
```

#### Expected Output

Shows a colon-separated list of directories.

---

### Command 4: `echo $SHELL`

#### Description

Displays the default shell currently being used.

#### Syntax

```bash
echo $SHELL
```

#### Expected Output

Shows the shell path (for example, `/bin/bash` or `/usr/bin/zsh`).

---

## Commands Executed

```bash
env
echo $HOME
echo $PATH
echo $SHELL
```

---

## Screenshot

```
screenshots/environment/lab-01-view-environment-variables.png
```

---

## Skills Gained

After completing this lab, I can:

- Display all environment variables.
- View my home directory.
- Identify the executable search path.
- Identify the current shell.

---

## Conclusion

This lab introduced Linux environment variables and demonstrated how to inspect important system variables used by the shell and applications.


---

# Lab 02 – Creating Environment Variables

## Objective

Learn how to create, display, export, and remove environment variables.

---

### Command 1: `NAME=Ridwan`

#### Description

Creates a shell variable named `NAME`.

#### Syntax

```bash
NAME=Ridwan
```

#### Expected Output

Creates the variable for the current shell session.

---

### Command 2: `echo $NAME`

#### Description

Displays the value stored inside the `NAME` variable.

#### Syntax

```bash
echo $NAME
```

#### Expected Output

Displays:

```text
Ridwan
```

---

### Command 3: `export NAME=Ridwan`

#### Description

Exports the variable, making it available to child processes started from the current shell.

#### Syntax

```bash
export NAME=Ridwan
```

#### Expected Output

The variable becomes part of the environment.

---

### Command 4: `unset NAME`

#### Description

Removes the variable from the current shell session.

#### Syntax

```bash
unset NAME
```

#### Expected Output

The variable is deleted.

---

### Command 5: `echo $NAME`

#### Description

Verifies that the variable has been removed.

#### Syntax

```bash
echo $NAME
```

#### Expected Output

No value is displayed.

---

## Commands Executed

```bash
NAME=Ridwan
echo $NAME
export NAME=Ridwan
unset NAME
echo $NAME
```

---

## Screenshot

```
screenshots/environment/lab-02-create-environment-variable.png
```

---

## Skills Gained

After completing this lab, I can:

- Create shell variables.
- Display variable values.
- Export variables to child processes.
- Remove variables from the current session.

---

## Conclusion

This lab demonstrated the lifecycle of environment variables, from creation and export to removal.


