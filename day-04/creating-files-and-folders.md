# Day 4 - Creating Files and Folders

## Commands practiced

### `mkdir`
Creates a new directory.

```bash
mkdir my-app
mkdir public
mkdir src
```

Multiple directories can also be created in one command:

```bash
mkdir images styles
```

### `touch`
Creates an empty file if it does not already exist.

```bash
touch README.md
touch package.json
```

Multiple files can be created in one command:

```bash
touch App.css App.js index.css index.js
```

### Creating a file inside another folder without changing directory

A relative path can be given directly to `touch`:

```bash
touch public/index.html
```

This creates `index.html` inside `public` while staying in the current directory.

### `mkdir -p`
Creates parent directories when they do not already exist.

```bash
mkdir -p components/Navbar
```

This creates `components` and then `Navbar` inside it in a single command.

## Exercise completed

Built this structure from the command line:

```text
my-app/
├── README.md
├── package.json
├── public/
│   └── index.html
└── src/
    ├── App.css
    ├── App.js
    ├── index.css
    ├── index.js
    └── components/
        └── Navbar/
```

## Main takeaways

- `mkdir` creates directories.
- `touch` creates empty files.
- One command can create multiple files or directories.
- Paths such as `public/index.html` let me create something inside another directory without `cd`-ing into it.
- `mkdir -p` can create nested directories in one command.
