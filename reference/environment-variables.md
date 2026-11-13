# Linux Environment Variables — Quick Reference

Prepared as a reference for a future review session. **This file is not a record of a completed study session.**

Environment variables allow programs and shell commands to read configuration such as executable search paths and language preferences.

## Inspect environment variables

```bash
# Print the current shell's PATH
echo "$PATH"

# List exported environment variables
printenv

# Print only the HOME variable
printenv HOME

# Check the location of an installed command
command -v python3
```

## Shell variables versus environment variables

```bash
# Local shell variable
PROJECT_NAME="linux-practice"
echo "$PROJECT_NAME"

# Export it so child processes inherit the value
export PROJECT_NAME

# Verify inheritance in a child shell
bash -c 'printf "%s\n" "$PROJECT_NAME"'

# Remove a variable from the current shell
unset PROJECT_NAME
```

A variable created without `export` normally stays inside the current shell and is not inherited by child processes.

## PATH essentials

The `PATH` variable is a colon-separated list of directories the shell searches for commands. To add a personal bin directory for the **current shell only**:

```bash
export PATH="$HOME/bin:$PATH"
```

Putting a directory first changes which executable may be found first. Avoid blindly adding untrusted directories to `PATH`.

## Temporary configuration for one command

```bash
LANG=C sort names.txt
```

Here `LANG=C` is set for this command invocation without permanently replacing the shell's normal `LANG` value.

## Review prompts

1. What is the difference between `NAME=value` and `export NAME=value`?
2. Why would `command -v python3` be useful?
3. Does a plain `export` survive opening a brand-new terminal?
4. What happens if a directory is prepended to `PATH`?

**Reminder:** Never commit secrets, access tokens, or real `.env` credentials into a repository. These examples contain only generic values.
