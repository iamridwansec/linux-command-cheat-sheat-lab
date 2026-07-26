# Search Files

## Introduction

The `grep` command is used to search for text patterns inside files. It is one of the most useful Linux commands for filtering output, finding strings in logs, and locating specific lines in documents.

---

## Table of Contents

- Lab 01 – Searching Text with grep
- Lab 02 – Case-Insensitive and Inverted Search
- Lab 03 – Recursive Search and Matched Output

---

# Lab 01 – Searching Text with grep

## Objective

Learn how to search for a word inside a file using `grep`.

## Example File

Create a file first:

```bash
cat > notes.txt

Command 1: grep Linux notes.txt
Description

Searches the file notes.txt for lines containing the word Linux.

Syntax
"grep Linux notes.txt"

Expected Output

Shows only the lines that contain Linux.

Real-world Use

Useful for finding specific words inside logs or notes.

Command 2: grep grep notes.txt
Description

Searches for the word grep inside notes.txt.

Syntax
"grep grep notes.txt"
Expected Output

Displays the line that contains grep.

Real-world Use

Useful when looking for a specific command or text in a file.

Commands Executed
cat > notes.txt
grep Linux notes.txt
grep grep notes.txt

Screenshot
screenshots/search/lab-01-grep-basic.png

Skills Gained

After completing this lab, I can:

Search for text inside a file.
Display only matching lines.
Use grep to find useful information quickly

Conclusion

This lab introduced the basic use of grep for searching text inside files.


Lab 02 – Case-Insensitive and Inverted Search
Objective

Learn how to ignore case while searching and how to show lines that do not match a pattern.

Command 1: grep -i linux notes.txt
Description

The -i option makes grep case-insensitive.

Syntax
"grep -i linux notes.txt"

Expected Output

Matches Linux, linux, or LINUX.

Real-world Use

Useful when you do not know the exact capitalization of the text.

Command 2: grep -v Linux notes.txt
Description

The -v option shows lines that do not match the pattern.

Syntax
"grep -v Linux notes.txt"

Expected Output

Displays every line except the ones containing Linux.

Real-world Use

Useful for filtering out unwanted lines from output.

Commands Executed
grep -i linux notes.txt
grep -v Linux notes.txt

Screenshot
screenshots/search/lab-02-grep-options.png

Skills Gained
After completing this lab, I can:

Search without worrying about uppercase or lowercase letters.
Show lines that do not match a pattern.
Filter file content more effectively.

Conclusion

This lab showed how grep -i and grep -v make text searching more flexible and powerful.

Lab 03 – Recursive Search and Matched Output
Objective

Learn how to search inside multiple files and display only the matching part of a line.

Command 1: grep -r Linux .
Description

The -r option searches recursively through files in the current directory and subdirectories.

Syntax
grep -r Linux .
Expected Output

Displays all files and lines containing Linux inside the current folder and subfolders.

Real-world Use

Useful for searching through project folders, logs, and source code.

Command 2: grep -o Linux notes.txt
Description

The -o option displays only the part of the line that matches the pattern.

Syntax
grep -o Linux notes.txt
Expected Output

Prints only Linux instead of the full line.

Real-world Use

Useful when you need only the exact matched text.

Commands Executed
grep -r Linux .
grep -o Linux notes.txt
Screenshot
screenshots/search/lab-03-grep-recursive.png
Skills Gained

After completing this lab, I can:

Search through folders recursively.
Show only the matched text.
Use grep for larger searches across many files.
Conclusion

This lab introduced recursive search and match-only output, making grep even more useful for real file searches.

