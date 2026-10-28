# Day 7 - Shortcuts & History

Today I completed the **Shortcuts & History** section of the Linux Command Line Bootcamp.

There was no exercise for this section, so I practiced some of the shortcuts a few times in the terminal.

## Shortcuts

- `Ctrl + L` - clear the screen
- `Ctrl + A` - move to the beginning of the line
- `Ctrl + E` - move to the end of the line
- `Ctrl + F` - move forward one character
- `Ctrl + B` - move backward one character
- `Alt + F` - move forward one word
- `Alt + B` - move backward one word
- `Ctrl + T` - swap the current character with the previous one
- `Ctrl + K` - delete from the cursor to the end of the line
- `Ctrl + U` - delete from the cursor to the beginning of the line
- `Alt + D` - delete from the cursor to the end of the word
- `Ctrl + W` / `Alt + Backspace` - delete backward through the beginning of the word
- `Ctrl + Y` - restore the most recently deleted text from the kill-ring

## Command History

- `history` - show previously used commands
- `history | less` - browse command history with `less`
- `!73` - re-run command number 73 from history
- `Ctrl + R` - reverse search through command history
- Press `Ctrl + R` again to cycle through other matches

Bash also stores command history in `~/.bash_history`.

## Note

I do not expect to remember every shortcut immediately. The goal is to recognize them and gradually build muscle memory by using them during normal terminal work.
