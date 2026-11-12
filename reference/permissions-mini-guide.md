# Linux file permissions — quick reference

Prepared reference material for a future study session. This is **not** a completed lesson or exercise.

## Read permission strings

Example: `-rwxr-xr--`

- First character: file type (`-` = regular file; `d` = directory).
- Next three: owner's permissions (`rwx`).
- Next three: group's permissions (`r-x`).
- Last three: others' permissions (`r--`).

The numbers are `r = 4`, `w = 2`, `x = 1`. Add each set:

| Mode | Owner | Group | Others |
| --- | --- | --- | --- |
| `644` | read/write | read | read |
| `755` | read/write/execute | read/execute | read/execute |
| `700` | read/write/execute | none | none |

## Commands to try later

```bash
# Inspect long-format permissions
ls -l

# Give the file owner execute permission
chmod u+x my-script.sh

# Set explicit file permissions
chmod 644 notes.txt

# Check the current username and group memberships
whoami
id

# Identify the directory and file you are working with
pwd
ls -ld .
```

## Important distinction: files vs directories

On a **file**, `x` allows execution (when it is otherwise executable). On a **directory**, `x` allows traversal into it; `r` allows listing directory entry names; and `w`, usually together with `x`, allows creating/removing entries. Directory write permission does not automatically grant permission to edit the contents of a file inside it.

## Three self-test questions

1. What permissions are represented by `750`?
2. Why might a user be unable to enter a directory even if it is readable?
3. What changes after `chmod u+x script.sh`?

Record actual attempts and outcomes in a future session after running them in a safe practice directory.
