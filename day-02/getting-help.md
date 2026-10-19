# Day 02 - Getting Help

Today I learned how to get help and documentation directly from the Linux terminal.

## man

`man` means manual. It opens the manual page for a command.

```bash
man ls
man ncal
man whoami
```

Press `q` to exit a man page.

## Reading a Synopsis

A command synopsis shows how the command can be used.

Example:

```text
bake [-btcek] RECIPE...
```

- `bake` = command
- `[-btcek]` = optional short options
- `RECIPE` = required argument
- `...` = more than one value can be allowed
- Anything inside `[ ]` is optional

Some options require an extra value.

```text
preheat [-cef] [-t number] [-d number]
```

For example, `-t` and `-d` require a number after them.

## Manual Sections

The Linux manual is divided into sections.

Section 1 contains user commands, which is the main section I am focusing on for now.

Example:

```bash
man 1 sort
```

## Searching the Manual

`man -k` searches manual page names and descriptions for a keyword.

```bash
man -k dog
```

The number shown in parentheses in the results is the manual section.

## type

`type` tells me what kind of command something is.

A command can be an executable program, shell built-in, shell function, or alias.

```bash
type echo
type date
```

In my exercise:

- `echo` was a shell built-in
- `date` was an executable at `/usr/bin/date`

## which

`which` shows the location of an executable program.

```bash
which mkdir
```

Example output:

```text
/usr/bin/mkdir
```

## help

Some commands are built directly into the shell and may not have their own man page.

For shell built-ins, `help` can be used.

```bash
help cd
help pwd
```

## Practice Commands

### whoami

```bash
man whoami
whoami
```

`whoami` prints the current effective user name. It does not require an argument.

### who

```bash
man who
who
```

`who` shows information about users currently logged in.

To show the most recent system boot time:

```bash
who -b
```
