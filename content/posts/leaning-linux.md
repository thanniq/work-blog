+++
author = "Thanni"
title = "Linux Crash Course"
date = "2023-12-28"
description = "Learning Linux"
tags = [
    "linux",
]
categories = [
    "Tutorial",
]
series = ["Devops"]
+++

Learn the fundamentals of Linux, exploring its features, and practical applications.

<!--more-->

Kernel: A compute program that forms the core of an operating system and manages critical tasks like:

- Memory management - task scheduling
- Managing hardware

Zsh 🔁 Bash

`~ > cash -s /bin/{bash orzsh}`

## Command Basics

`ncal` to check the calendar

`sort filename.txt` to sort info inside a text file

`rm filename.ext` to remove the file

Long Form Options

`-r` - for options `--` universal for long names

## Getting Help

`man "command"` to get help, q to quit

Synopsis - `[]` - means optional

`[-tkbs]` means -t, -k, -b, and they are optional

`FILENAME`... means can accept multiple filenames, but it's not optional

`[FILENAME]`... - means can accept multiple filenames but optional

## The Type & Which Commands

`type "echo"` - to know which class a command is.

## Navigation

### Root

`/` - The root directory

```
/

/ drills into
bin - home - root - dev - var and others

/home drill into users
thanni
```

On Linux, `xdg-open /` to access the top directory

On a Mac, you can use `open /` to access the top directory.

### Home

The second important directory is called `/home`, which contains a folder for each user.

`/` - refers to root

`~` - refers to the home

### `pwd` (print working directory)

The print working directory command is super simple but very useful. Think of it as a "where am I" command. It will print the path of your current working directory, starting from the root / For example, if I were on my desktop and I ran pwd, I would see /home/colt/Desktop

### `ls`

List the content of a directory

**ls options**

The ls command accepts a ton of options. Two of the more commonly used are -l and -a

`ls -l` - (lowercase L) prints in long listing format. It shows far more information about each file/folder

`ls -a` - the -a option will also list any hidden files that begin with `.` . These are normally not listed

`ls -la` - We can combine options! This example prints detailed information for all files, including hidden files.

### `cd`

The cd command changes the current working directory, "moving" into another directory. For example... cd chickens would change into the chickens directory (assuming it exists) cd /home/colt would take me my home directory

### Going back

In Unix-like operating systems, a single dot (.) is used to represent the current directory. Two dots (..) represent the parent directory. So we can use cd .. to move up one level, from our current directory into the parent directory. `cd ~` to go straight back to home.

### Relative and Absolute Paths

Relative paths are paths that specify a directory/file relative to the current directory. e.g /home/colt

We can use absolute paths to specify a location no matter our current location. But they start from the root directory - `/`.

## Creating Files & Folders

<mark>Learning in progress</mark>
