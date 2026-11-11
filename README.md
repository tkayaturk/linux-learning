# Linux Command Line Learning

My hands-on notes and exercises from the **Linux Command Line Bootcamp**. This repository documents commands I have practiced in Ubuntu while learning Linux fundamentals for backend, cloud, and DevOps work.

## Study log

| Session | Notes |
| --- | --- |
| [Day 01](day-01/) | Linux study notes |
| [Day 02](day-02/) | Linux study notes |
| [Day 03](day-03/) | Linux study notes |
| [Day 04](day-04/) | Linux study notes |
| [Day 05](day-05/) | Linux study notes |
| [Day 06](day-06/) | Linux study notes |
| [Day 07](day-07/) | Linux study notes |
| [Day 08](day-08/working-with-files.md) | Reading, inspecting, counting, and sorting files |
| [Day 09](day-09/redirection.md) | Standard streams, redirection, and wildlife survey exercise |

## Command quick reference

```bash
# Inspect file contents
cat -n notes.txt
less notes.txt
head -n 5 notes.txt
tail -n 5 notes.txt

# Count and sort
wc -l notes.txt
sort -u names.txt > unique-names.txt

# Combine files and append new information
cat first.txt second.txt > combined.txt
date >> combined.txt

# Redirect standard output and errors
cat missing.txt 2> errors.txt
ls existing-folder missing-folder > output.txt 2>&1
```

**What these commands reinforce:**
- `>` overwrites a file with standard output; `>>` appends standard output.
- `2>` redirects standard error; `2>>` appends standard error.
- `sort -u` sorts lines and removes duplicate entries.
- `cat` combines file contents but does not sort them.

## Practice highlight: Wildlife survey

The [Day 09 exercise](day-09/redirection.md#exercise-peruvian-amazon-wildlife-survey) combined three survey files, sorted unique species, appended a new observation, and recorded a command error using Bash redirection.

## Next steps

Practice shell pipelines and revisit the commands without looking at notes before moving to more advanced Linux topics.

> This README is a navigation and reference update. It does not represent a new study session.

## Common redirection mistakes (review notes)

These are quick reminders based on earlier command-line exercises, not a new study session.

| Goal | Command | Reminder |
| --- | --- | --- |
| Combine three files | `cat a.txt b.txt c.txt > all.txt` | The destination is overwritten. |
| Remove duplicate lines | `sort -u all.txt > unique.txt` | `sort -u` also puts lines in order. |
| Add the current date | `date >> unique.txt` | `>>` appends without removing prior lines. |
| Save an error message | `cat missing.txt 2>> errors.txt` | `2>>` appends **stderr**, not stdout. |
| Save both output streams | `command > run.log 2>&1` | Redirect stdout first, then stderr to the same destination. |

**Self-check:** What happens if you use `>` instead of `>>` when adding the date? The earlier content gets replaced. When testing a missing file, use a file that is intentionally absent; otherwise there may be no error to redirect.

## Restart checklist (prepared reference)

This checklist is for the **next** hands-on session. Adding it is documentation maintenance and does not imply the exercises were completed today.

- [ ] Explain the difference between `>`, `>>`, `2>`, and `2>>` without notes.
- [ ] Recreate the wildlife-survey solution: concatenate, sort unique species, then append another line.
- [ ] Practice `grep -i`, `wc -l`, and `sort -nr` with a small test file.
- [ ] Compare `sort -u file.txt` with `sort file.txt | uniq`.
- [ ] Use a pipeline to count matching lines and redirect the result to a file.

After completing them, record the commands actually used and any errors encountered in a new study-log entry.
