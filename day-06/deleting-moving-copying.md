# Day 6 - Deleting, Moving and Copying

Today I practiced basic Linux file and directory management commands.

## Commands learned

### Remove files
```bash
rm file.txt
```

### Remove directories
Empty directory:
```bash
rm -d foldername
```

Non-empty directory:
```bash
rm -r foldername
```

### Move files or folders
```bash
mv source destination
```

Example:
```bash
mv Netta.txt ..
```

### Rename files or folders
```bash
mv oldname newname
```

Example:
```bash
mv Sara.txt Sarah.txt
```

### Copy files
```bash
cp source destination
```

### Copy directories recursively
```bash
cp -r source_folder destination_folder
```

## Practice exercise

I completed a Bootcamp directory exercise where I:
- Created `FallCohort`, `WinterCohort`, and `Waitlist` directories
- Created multiple `.txt` files with `touch`
- Deleted `Edgar.txt`
- Moved `Netta.txt` from `Waitlist` to `FallCohort`
- Deleted the non-empty `Waitlist` directory with `rm -r`
- Renamed `Sara.txt` to `Sarah.txt`
- Moved `Italo.txt` from `FallCohort` to `WinterCohort`
- Copied `WinterCohort` to `SpringCohort` using `cp -r`
- Renamed `WinterCohort` to `WinterCohortCANCELLED`
- Deleted the entire `BootCamp` directory

## Useful habit

When I was unsure how to copy a directory, I used:
```bash
man cp
```
This helped me find the recursive `-r` option myself.
