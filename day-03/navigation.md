# Day 3 - Navigation

## Commands learned

### `pwd`
Shows the current working directory.

```bash
pwd
```

### `ls`
Lists the contents of a directory.

```bash
ls
```

Useful options:

```bash
ls -l
```
Shows a detailed list.

```bash
ls -a
```
Shows hidden files too.

```bash
ls -la
```
Combines detailed view and hidden files.

### `cd`
Changes the current directory.

```bash
cd FolderName
```

Go to the parent directory:

```bash
cd ..
```

## Relative and absolute paths

- Relative path: starts from the current directory.
- Absolute path: starts from the filesystem root `/`.
- `.` means the current directory.
- `..` means the parent directory.

## Sorting with `ls`

### Sort by modification time

```bash
ls -lt
```
Newest files appear first.

```bash
ls -ltr
```
Reverses the order, so the oldest files appear first.

### Sort by file size

```bash
ls -lS
```
Largest files appear first.

## Farm exercise

I practiced navigating through a prepared `Farm` directory using the terminal.

What I did:

- Listed the contents of `Farm`.
- Entered `Coop` and then `Chickens`.
- Counted 6 chicken files.
- Used modification-time sorting to find the oldest chicken: `Elvis` (1980).
- Moved from `Chickens` to the sibling `Geese` directory using a relative path.
- Counted 4 goose files.
- Used size sorting to find the largest goose file: `Muffin`.
- Navigated to `Stable/Horses`.
- Counted 4 normally visible horse files.
- Used `ls -a` to find the hidden horse file: `.troy`.

## Main idea

Navigation commands answer three basic questions:

- `pwd` -> Where am I?
- `ls` -> What is here?
- `cd` -> Where do I want to go?
