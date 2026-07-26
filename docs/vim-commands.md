# Vim Commands

## Introduction

Vim is a terminal-based text editor used to create and edit files directly from the Linux command line. It is especially useful when working over SSH or on systems without a graphical interface.

---

## Table of Contents

- Lab 01 – Insert Mode and Saving Files
- Lab 02 – Opening New Lines
- Lab 03 – Deleting and Changing Text
- Lab 04 – Undo, Replace, and Case Change

---

# Lab 01 – Insert Mode and Saving Files

## Objective

Learn how to open a file in Vim, enter insert mode, type text, save the file, and quit Vim.

## Example File

```bash
vim practice.txt
Command 1: i
Description

The i command enters insert mode so text can be typed at the cursor position.

Syntax
"i"
Example

Open the file, move the cursor, then press i to start typing.

Expected Output

Vim switches to insert mode and allows text input.


Command 2: ESC
Description

The ESC key exits insert mode and returns Vim to normal mode.

Syntax
"ESC"

Example

Press ESC after typing text.

Expected Output

You return to normal mode.

Command 3: :w
Description

The :w command saves the current file without closing Vim.

Syntax
":w"

Example

After typing text, press ESC and type :w.

Expected Output

The file is written to disk.


Command 4: :wq
Description

The :wq command saves the file and exits Vim.

Syntax
":wq"

Example

After saving, type :wq to close Vim.

Expected Output

The file is saved and Vim closes.

Commands Executed

vim practice.txt
i
ESC
:w
:wq


```markdown
# Lab 03 – Deleting and Changing Text

## Example File

```bash
vim practice.txt
