# Day 8 - Working With Files

Today I completed the **Working With Files** section of the Linux Command Line Bootcamp and practiced the commands with `poem.txt` and `purchases.txt`.

## Reading Files

- `cat file.txt` - print the entire contents of a file
- `cat -n file.txt` - print the file with line numbers
- `less file.txt` - read a file one page at a time
- `less -N file.txt` - open a file in `less` with line numbers
- `less -I file.txt` - use case-insensitive searches in `less`

### Useful `less` navigation

- `Enter` / Down Arrow - move down one line
- Up Arrow - move up one line
- `Space` / `f` - move down one page
- `b` - move up one page
- `/pattern` - search for text
- `n` - go to the next search match
- `q` - quit
- `50%` - jump to approximately 50% of the file

## Reversing File Output

- `tac file.txt` - print the lines of a file in reverse order
- `rev file.txt` - reverse the characters on each line

## Viewing the Beginning and End of Files

- `head file.txt` - print the first 10 lines by default
- `head -n 4 file.txt` - print the first 4 lines
- `head -4 file.txt` - shorter syntax for the first 4 lines
- `head -c 8 file.txt` - print the first 8 bytes
- `tail file.txt` - print the last 10 lines by default
- `tail -n 8 file.txt` - print the last 8 lines

## Counting With `wc`

- `wc file.txt` - show line, word, and byte counts
- `wc -l file.txt` - count lines
- `wc -w file.txt` - count words
- `wc -c file.txt` - count bytes

## Sorting Files

- `sort file.txt` - sort lines alphabetically
- `sort -r file.txt` - reverse the sorting order
- `sort -n file.txt` - sort numerically
- `sort -u file.txt` - sort and show only unique lines
- `sort -n -k3 file.txt` - sort numerically using the third field
- `sort -nr -k3 file.txt` - sort numerically by the third field in reverse order

## Practice

I practiced with two files:

### `poem.txt`

- Printed the full file with line numbers
- Navigated through the file using `less`
- Searched for `Dog` and performed a case-insensitive search for `dog`
- Opened the file with line numbers in `less`
- Jumped to 50% of the file
- Counted the words
- Printed the first 4 lines
- Printed the last 8 lines

### `purchases.txt`

- Printed the lines in reverse order
- Sorted the file alphabetically
- Counted the number of lines
- Sorted the data numerically by the price column
- Reversed the numeric sort to show the highest prices first

## Note

The main goal today was to become more comfortable reading, inspecting, counting, and sorting file contents directly from the terminal.
