# Beginner's Guide to Unix on Windows and macOS

Welcome to this beginner-friendly tutorial that will guide you through setting up a Unix environment on Windows and macOS, installing Git, and getting started with GitHub. By the end of this guide, you'll be comfortable running Unix commands, using Git for version control, and collaborating on projects using GitHub.

---

## Table of Contents

- [Beginner's Guide to Unix on Windows and macOS](#beginners-guide-to-unix-on-windows-and-macos)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Setting Up a Unix Environment](#setting-up-a-unix-environment)
    - [macOS](#macos)
    - [Windows](#windows)
      - [Using Windows Command Prompt](#using-windows-command-prompt)
      - [Using Git Bash](#using-git-bash)
  - [Basic Unix Commands](#basic-unix-commands)
  - [Basic Windows CLI Commands](#basic-windows-cli-commands)

---

## Introduction

**Unix** is a powerful operating system that serves as the foundation for many modern platforms, including Linux and macOS. **Git** is a distributed version control system that allows you to track changes in your code. **GitHub** is a web-based platform that hosts Git repositories, enabling collaboration among developers.

This guide will help you:

- Set up a Unix-like environment on your Windows or macOS machine.
- Learn basic Unix commands.
- Install and configure Git.
- Understand fundamental Git operations.
- Use GitHub for hosting and collaborating on projects.

---

## Setting Up a Unix Environment
Unix commands are instructions that you type into a terminal, or command-line interface (CLI) to interact with the operating system. These commands allow you to perform a variety of tasks, from navigating the file system and managing files to controlling system processes and network settings.

### macOS

**Open Terminal:**
    - Terminal is pre-installed on macOS. You can find it in the **Applications** > **Utilities** folder or by searching for "Terminal" in Spotlight. (Press `cmd + spacebar`).

### Windows

#### Using Windows Command Prompt
If you search for `cmd` in the Start menu you will find the **Windows Command Prompt**. Here You can run commands to navigate around your file system (*directory*). While these aren't unix commands, many commands are very similare. To find any specific commands you can use the command `help`.

#### Using Git Bash

1. **Download and Install Git:**
   
   - If you already have git installed on your windows machine, then you have the Git Bash terminal program in your system.

2. **Open Git Bash:**

   - After installation, you can open Git Bash from the Start menu. In this terminal window you can use the same unix commands that can be used in macOS or Linux.

---

## Basic Unix Commands

Let's familiarize ourselves with some basic **Unix commands**, to be used in macOS Terminal or Git Bash.

- **Navigation Commands:**

  - `pwd`: Print Working Directory.

    ```bash
    pwd
    ```

  - `ls`: List directory contents.

    ```bash
    ls
    ls -l    # Long format listing
    ls -a    # Include hidden files
    ```

  - `cd`: Change Directory.

    ```bash
    cd /path/to/directory
    cd ~     # Navigate to home directory
    cd ..    # Move back one directory
    ```

- **File Operations:**
  
  Remember that refering to files and folders in the terminal can be a bit tricky. Since spaces are used to separate commands, you new to use backslash `\` to 'escape' spaces in file and folder names. If I have a folder named `folder name` I have to refer to it as `folder\ name` in the terminal. Also, you have to use complete names in the terminal. If a file is named `filename.txt` you can't write `filename` since the terminal won't find that file.

  - `touch`: Create a new file.

    ```bash
    touch filename.txt
    ```

  - `mkdir`: Make a new directory.

    ```bash
    mkdir myfolder
    ```

  - `cp`: Copy files or directories.

    ```bash
    cp source.txt destination.txt
    cp -r sourcedir/ destinationdir/
    ```

  - `mv`: Move or rename files or directories.

    ```bash
    mv oldname.txt newname.txt
    mv file.txt /path/to/destination/
    ```
    Remember that you have to enter the entire file name, including suffixes like `.txt` or `.pdf` etc.

  - `rm`: Remove files or directories.

    ```bash
    rm filename.txt     # For removing individual files.
    rm -r directoryname/    # the '-r' flag needed to remove whole directories
    ```

- **Viewing File Contents:**

  - `cat`: Concatenate and display file content.

    ```bash
    cat filename.txt
    ```

  - `less`: View file content one page at a time.

    ```bash
    less filename.txt
    ```

- **Others:**

  - `echo`: Display a line of text.

    ```bash
    echo "Hello, World!"
    ```

  - `man`: Display the manual page for a command.

    ```bash
    man ls
    ```
    (Press q to exit manual.)

**Tip:** Use `Ctrl + L` to clear the terminal screen.

---

## Basic Windows CLI Commands

If you prefer using the standard Windows Command Line Interface (CLI) where unix can't be used, here are some basic commands:

- **Navigation Commands:**

  - `cd`: Change Directory.

    ```cmd
    cd folder-name
    cd \path\to\directory
    cd %HOMEPATH%  # Navigate to home directory
    cd ..          # Move back one directory
    ```
    (You can use Tab to complete folder names for quick navigation.)

  - `dir`: List directory contents.

    ```cmd
    dir
    dir /A  # Include hidden files
    ```

- **File Operations:**

  - `copy`: Copy files.

    ```cmd
    copy source.txt destination.txt
    ```

  - `move`: Move or rename files.

    ```cmd
    move oldname.txt newname.txt
    move file.txt \path\to\destination\
    ```

  - `mkdir`: Make a new directory.

    ```cmd
    mkdir myfolder
    ```

  - `del`: Delete files.

    ```cmd
    del filename.txt
    ```

  - `rmdir`: Remove directories.

    ```cmd
    rmdir directoryname
    ```

- **Viewing File Contents:**

  - `type`: Display file content.

    ```cmd
    type filename.txt
    ```

- **Others:**

  - `echo`: Display a line of text.

    ```cmd
    echo Hello, World!
    ```

  - `cls`: Clear the screen.

    ```cmd
    cls
    ```

**Tip:** Use `Ctrl + C` to terminate a running command.

---