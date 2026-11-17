# Cron: scheduling recurring Linux commands

A reference sheet for a future Linux/DevOps practice session. This is **prepared study material**, not a claim that a new lesson or hands-on task has been completed.

## Cron expression layout

A user crontab entry generally has five time fields followed by a command:

```text
minute hour day-of-month month day-of-week command
  0     9        *        *       1-5    /path/to/script.sh
```

This example schedules a script at 09:00 Monday–Friday, based on the cron daemon's configured timezone.

| Field | Typical range | Example |
| --- | --- | --- |
| Minute | 0–59 | `30` |
| Hour | 0–23 | `18` |
| Day of month | 1–31 | `*` |
| Month | 1–12 | `*` |
| Day of week | 0–7 (Sunday = 0 or 7) | `1-5` |

## Reference commands

```bash
# List cron entries for the current user
crontab -l

# Edit the current user's cron entries
crontab -e

# Look up where commands are installed
command -v bash
command -v python3
```

Example entry: run a script every day at 18:30 and append output and errors to a log.

```cron
30 18 * * * /bin/bash /home/USER/scripts/backup.sh >> /home/USER/logs/backup.log 2>&1
```

Replace `USER` and ensure the script and log directory exist. **Do not paste the placeholder directly into your real crontab.**

## Common pitfalls

- Cron has a minimal environment; rely on explicit paths and set needed environment variables in the job.
- Use `>>` to append logs; `>` overwrites the previous log content.
- A script can work interactively but fail in cron due to its working directory or missing environment.
- The weekday and day-of-month fields interact in cron implementations; avoid combining specific values unless you know the matching behavior.
- Test the command manually before scheduling it. Use `crontab -l` to review entries after editing.
- Never place passwords or API tokens directly in crontab commands.

## Review questions

1. How would you schedule a command every 15 minutes?
2. What is different about `30 18 * * *` and `0 18 * * *`?
3. Why might a job find `python3` in your terminal but not under cron?

Complete and record a real test during a future study session.
