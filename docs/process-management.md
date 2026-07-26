#Basic Process Management Commands

> **Operating System:** Kali Linux 2026.x  
> **Shell:** Zsh  
> **Author:** Ridwan  
> **Purpose:** Practical documentation of basic Linux commands with screenshots and explanations.

This document contains the basic Linux commands executed during this lab.

# Process Management

## Introduction

Process management is an important part of Linux administration. A process is a running program, and Linux provides commands to view, monitor, prioritize, and terminate processes. These commands are useful for troubleshooting system performance and controlling running services.

---

## Table of Contents

- Lab 01 – Viewing Running Processes
- Lab 02 – Finding Process IDs
- Lab 03 – Terminating Processes
- Lab 04 – Process Priority
- Lab 05 – Disk and Memory Usage

---

# Lab 01 – Viewing Running Processes

## Objective

Learn how to view running processes using `ps` and `top`.

---

### Command 1: `ps`

#### Description

The `ps` (Process Status) command shows a snapshot of the processes running in the current shell session.

#### Syntax

```bash
ps
```

#### Expected Output

Displays process information such as the process ID (PID), terminal, CPU time, and command name.

---

### Command 2: `top`

#### Description

The `top` command shows running processes in real time. It updates continuously and displays CPU and memory usage.

#### Syntax

```bash
top
```

#### Expected Output

Displays a live table of active processes.

> Press `q` to exit `top`.

---

## Commands Executed

```bash
ps
top
```

---

## Screenshot

```
screenshots/processes/lab-01-viewing-processes.png
```

---

## Skills Gained

After completing this lab, I can:

- View currently running processes.
- Monitor processes in real time.
- Identify basic process information.
- Exit an interactive process monitor.

---

## Conclusion

This lab introduced the basic commands for viewing running processes in Linux. I learned how to check active processes with `ps` and monitor them live with `top`.

---

# Lab 02 – Finding Process IDs

## Objective

Learn how to find the process ID of a running program and inspect a specific process.

---

### Command 1: `pidof bash`

#### Description

The `pidof` command returns the process ID of a running program.

#### Syntax

```bash
pidof bash
```

#### Expected Output

Displays the PID of the `bash` process.

---

### Command 2: `ps -p PID`

#### Description

The `ps` command can be used to inspect a specific process by its PID.

> Your instructor wrote `ps PID`, but the normal Linux syntax is `ps -p PID`.

#### Syntax

```bash
ps -p 1234
```

#### Expected Output

Displays information about the process with PID `1234`.

---

## Commands Executed

```bash
pidof bash
ps -p 1234
```

---

## Screenshot

```
screenshots/processes/lab-02-finding-process-ids.png
```

---

## Skills Gained

After completing this lab, I can:

- Find the process ID of a running program.
- Inspect a specific process using its PID.
- Understand how to identify processes before managing them.

---

## Conclusion

This lab showed how to locate process IDs and inspect individual processes. That skill is important when troubleshooting or deciding which process to terminate.

---

# Lab 03 – Terminating Processes

## Objective

Learn how to stop processes using `kill`, `pkill`, and `killall`.

---

### Command 1: `kill PID`

#### Description

The `kill` command sends a signal to a process using its PID. It is commonly used to stop a process.

#### Syntax

```bash
kill PID
```

#### Expected Output

The process with PID `1234` is terminated if the signal is accepted.

---

### Command 2: `pkill name`

#### Description

The `pkill` command stops processes by name instead of PID.

#### Syntax

```bash
pkill name
```

#### Expected Output

All matching processes with the specified name are terminated.

---

### Command 3: `killall name`

#### Description

The `killall` command terminates all processes whose names begin with the specified name.

#### Syntax

```bash
killall name
```

#### Expected Output

All processes matching the name are stopped.

---

## Commands Executed

```bash
kill 1234
pkill firefox
killall firefox
```

---

## Screenshot

```
screenshots/processes/lab-03-terminating-processes.png
```

---

## Skills Gained

After completing this lab, I can:

- Terminate a process using its PID.
- Stop processes by name.
- Use different commands to manage running programs.
- Understand process termination in Linux.

---

## Conclusion

This lab introduced the main commands used to stop running processes. I learned how to terminate programs using a PID or a process name.

---

# Lab 04 – Process Priority

## Objective

Learn how to start and adjust the priority of processes using `nice` and `renice`.

---

## `nice` – Start a Process with a Custom Priority

**Syntax**
```bash
nice -n <priority> <command>
```

**Example**
```bash
$ nice -n 10 sleep 100
```

**Expected Output**
```bash
# No output is displayed.
# The process starts in the background (if '&' is used) or runs silently.
```

**Verify the Priority**
```bash
$ ps -o pid,ni,comm -C sleep
```

**Example Output**
```text
  PID  NI COMMAND
 4321  10 sleep
```

---

## `renice` – Change the Priority of a Running Process

**Syntax**
```bash
renice <priority> -p <PID>
```

**Example**
```bash
$ renice 10 -p 4321
```

**Expected Output**
```text
4321 (process ID) old priority 0, new priority 10
```

**Verify the Change**
```bash
$ ps -o pid,ni,comm -p 4321
```

**Example Output**
```text
  PID  NI COMMAND
 4321  10 sleep
```

## Skills Gained

After completing this lab, I can:

- Start a process with a specified priority.
- Change the priority of a running process.
- Understand process scheduling at a basic level.

---

## Conclusion

This lab introduced process priority control using `nice` and `renice`. I learned how Linux manages process scheduling and priority values.

---

# Lab 05 – Disk and Memory Usage

## Objective

Learn how to check free disk space and available memory using `df` and `free`.

---

### Command 1: `df`

#### Description

The `df` command shows available and used disk space on mounted filesystems.

#### Syntax

```bash
df
```

#### Expected Output

Displays disk usage for each mounted filesystem.

---

### Command 2: `free`

#### Description

The `free` command shows memory usage, including RAM and swap space.

#### Syntax

```bash
free
```

#### Expected Output

Displays total, used, free, shared, cached, and available memory.

---

## Commands Executed

```bash
df
free
```

---

## Screenshot

```
screenshots/processes/lab-05-disk-memory-usage.png
```

---

## Skills Gained

After completing this lab, I can:

- Check available disk space.
- Check memory usage.
- Understand system resource usage at a basic level.

---

## Conclusion

This lab introduced the Linux commands used to monitor disk space and memory usage. These commands help administrators keep an eye on system resources.


---

# Lab 06 – Checking Disk Usage

## Objective

Learn how to check available disk space on mounted filesystems.

---

### Command 1: `df`

#### Description

The `df` command shows the amount of disk space used and available on mounted filesystems.

#### Syntax

```bash
df
```

#### Expected Output

Displays disk usage information for each mounted filesystem.

---

## Commands Executed

```bash
df
```

---

## Screenshot

```
screenshots/processes/lab-06-disk-usage.png
```

---

## Skills Gained

After completing this lab, I can:

- Check disk usage on mounted filesystems.
- Identify used and available storage space.
- Understand basic filesystem capacity information.

---

## Conclusion

This lab introduced the `df` command, which is used to monitor disk space usage on Linux systems.
