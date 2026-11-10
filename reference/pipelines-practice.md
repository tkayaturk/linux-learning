# Shell pipelines: practice reference

A short reference for revisiting Linux commands already covered in the learning log. This is a practice sheet, **not** a claim that a new lesson or exercise has been completed.

## What a pipe does

A pipe (`|`) passes the **standard output** of one command to the **standard input** of the next.

```bash
# Find lines containing the word error, ignoring capitalization
grep -i 'error' app.log

# Count matching lines
grep -i 'error' app.log | wc -l

# Read the five most common names, after sorting and counting
sort names.txt | uniq -c | sort -nr | head -n 5
```

## A small reproducible exercise

Create a test file:

```bash
printf 'apple\nbanana\napple\npear\nbanana\napple\n' > fruit.txt
```

Then try these commands:

| Task | Command |
| --- | --- |
| Show unique fruit names in alphabetical order | `sort -u fruit.txt` |
| Count each fruit | `sort fruit.txt \| uniq -c` |
| Display the most frequent fruit first | `sort fruit.txt \| uniq -c \| sort -nr` |
| Save only unique names | `sort -u fruit.txt > unique-fruit.txt` |

Expected count order: `apple` appears 3 times, `banana` 2, and `pear` 1.

## Common pitfalls

- `uniq` removes **adjacent** repeated lines, so use `sort | uniq` to count duplicates throughout an unsorted file.
- `|` connects commands; `>` writes output to a file.
- `grep pattern file | wc -l` counts matching **lines**, not the number of occurrences within each line.
- Standard errors are not sent through an ordinary pipe automatically. When appropriate, `2>&1` can combine the streams.

## Self-check questions

1. Why is `sort` used before `uniq -c`?
2. How would you show only the top two most frequent items?
3. What changes when `>` is replaced with `>>`?

The goal is to solve these from memory during the next real study session.
