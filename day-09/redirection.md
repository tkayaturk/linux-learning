# Day 9 - Redirection

**Date:** November 3, 2026  
**Course:** Linux Command Line Bootcamp  
**Topic:** Standard streams and shell redirection

Today I studied redirection in Bash, reviewed yesterday's file commands, practiced redirecting normal output and errors, and completed the **Wildlife Survey** exercise using the terminal.

## Standard Streams

Linux commands use three standard streams:

| Descriptor | Stream | Purpose |
| --- | --- | --- |
| `0` | stdin | Standard input supplied to a command |
| `1` | stdout | Normal command output |
| `2` | stderr | Error messages |

By default, normal output and errors both appear in the terminal, but they are separate streams.

## Redirection Operators

| Operator | Meaning | Example |
| --- | --- | --- |
| `>` | Write stdout to a file (overwrite existing contents) | `echo "Hello" > message.txt` |
| `>>` | Append stdout to a file | `echo "Git" >> notes.txt` |
| `<` | Read stdin from a file | `sort < names.txt` |
| `2>` | Write stderr to a file (overwrite) | `cat missing.txt 2> errors.txt` |
| `2>>` | Append stderr to a file | `cat missing.txt 2>> errors.txt` |
| `2>&1` | Send stderr to stdout's current destination | `ls docs > result.txt 2>&1` |
| `&>` | Redirect both stdout and stderr to one file (Bash) | `ls docs missing &> result.txt` |
| `&>>` | Append both stdout and stderr to one file (Bash) | `ls docs missing &>> result.txt` |

Important notes:
- `>` and `2>` can overwrite existing file contents.
- `>>` and `2>>` preserve existing contents and append new output.
- `2>` redirects the **error stream**; it is not an `if` condition that checks whether an error occurred.
- When using `2>&1`, order matters: `> result.txt 2>&1` directs both streams to the file.

## Guided Practice

I wrote the following commands during practice:

```bash
# Append a line without deleting previous content
echo Git >> notlar.txt

# Save an error instead of printing it on screen
cat olmayan.txt 2> hatalar.txt

# Save normal output and errors together
ls belgeler olmayan_klasor &> sonuc.txt

# Sort input from a file and save the result to another file
sort < isimler.txt > sirali.txt

# Save standard output separately and append errors separately
cat dosya1.txt olmayan.txt > sonuc.txt 2>> hatalar.txt
```

I initially used `cat` instead of `sort` in the fourth task. I corrected it after realizing that `cat` copies/displays text but does not alphabetize it.

## Exercise: Peruvian Amazon Wildlife Survey

**Goal:** Combine three assistants' wildlife observations, remove duplicates, sort species, and append a new observation and an error message.

### Step 1 - Combine survey files

```bash
cat angela-survey.txt nico-survey.txt juan-survey.txt > all-species.txt
```

Combines all three files into one new file in a single command.

### Step 2 - Sort alphabetically and remove duplicates

```bash
sort -u all-species.txt > sorted-animals.txt
```

`sort -u` sorts the lines and keeps one copy of each duplicate entry.

### Step 3 - Append the current date and the new species

```bash
date >> sorted-animals.txt
echo Green Anaconda >> sorted-animals.txt
```

Both commands append to the existing file rather than overwrite it.

### Step 4 - Append the error from a nonexistent command

```bash
ughhh 2>> sorted-animals.txt
```

The shell error produced by the nonexistent `ughhh` command is appended to the same file.

**Outcome:** Completed the exercise in the Ubuntu terminal, using the expected redirection and sorting logic. The commands above show the complete filenames from the assignment; I abbreviated the filenames when reporting my work in chat.

## Review of Day 8

Before starting today's topic, I reviewed:
- `cat` and `less` for reading files
- `head` and `tail` for selecting lines
- `wc -l` and `wc -w` for counting
- `sort`, `sort -r`, `sort -n`, and `sort -u`
- `tac` for reversing **line order** rather than sorting lines
- `less` navigation: `Space` and `b` move between pages; `n` and `N` move between search matches

## What I Learned

I can now use multiple redirection operators in a single Bash command, separate normal output from errors, and combine `cat`, `sort`, `date`, and `echo` to solve a practical file-processing exercise.

**Next step:** Continue the Linux course and revisit stream redirection with new exercises if needed.
