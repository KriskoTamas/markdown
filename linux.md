# Linux cheat sheet

## Help
Show help page
```
help
```

## Util commands
Clear terminal display
```
clear
```

Show terminal history
```
history
```

Show current date and time
```
date
```

Display disk filesystem information
```
df
```

Print text
```
echo [text]
```

Write text to file
```
echo [text] > [file]
```

Append to end of file
```
echo [text] >> [file]
```

Display file contents
```
cat [file]
```

Display last 10 rows of file
```
tail [file]
```

Display last N rows of file
```
tail -n [number] [file]
```

## Managing files

### Creating

Create directory
```
mkdir [directory] [directory...]
```

Create file
```
touch [file] [file...]
```

### Deleting

Remove empty directory
```
rmdir [directory] [directory...]
```

Remove directory and its contents
```
rm -r [directory] [directory...]
```

Remove file or files
```
rm [file] [file...]
```

### Copying
Copy to another directory
```
cp [sourcePath] [targetPath]
```

Copy and rename file or directory
```
cp [sourcePath] [targetPath]/[newName]
```

### Moving
Files and directories can be moved with the same `mv` command

Move to another directory
```
mv [sourcePath] [targetPath]
```

Move up one level
```
mv [sourcePath] .
mv [sourcePath] ..
mv [sourcePath] ./.
```

Move up two levels
```
mv [sourcePath] ./..
mv [sourcePath] ../.
```

### Renaming

Rename file or directory
```
mv [oldName] [newName]
```

Rename and move file or directory
```
mv [sourcePath] [targetPath]/[newName]
```

### Managing permissions
Change permissions of one or more files
```
chmod [mode] [file...]
```

**[mode]** can be:
- Symbolic mode
- Numeric mode

When using *symbolic* mode, we can use the following syntax to manage permissions:
**[who][what][which]**

**[who]** can be:

- `u`: User, meaning the owner of the file.
- `g`: Group, meaning members of the group the file belongs to.
- `o`: Others, meaning people not governed by the u and g permissions.
- `a`: All, meaning all of the above.

**[what]** can be:

- `+`: Plus sign. Grants the permission. The permission is added to the existing permissions.
- `–`: Minus sign. Removes the permission.
- `=`: Equals sign. Set a permission and remove others.

**[which]** can be:

- `r`: The read permission.
- `w`: The write permission.
- `x`: The execute permission.

Few examples:
- `a+x`: Adds execute permission for all.
- `g-w`: Removes write permission from group.
- `u=rwx`: Sets read, write and execute permissions for the user.
- `u=rw,og=r`: Sets read and write for user and read for others and group.

When using *numeric* mode, we can use the following syntax to manage permissions:
**[user][group][others]**

Each of these represented by a number:

- `0`: No permission
- `1`: Execute
- `2`: Write
- `4`: Read

Basically, you add up the numbers depending on the level of permission you want to give.

Few examples:
- `777`: Sets all permissions to all users.
- `744`: Sets read, write and execute for user, read for group and others.
- `111`: Sets execute permission to all users.
- `0` or `-`: No permission to all.

## Changing directory
Change current working directory to HOME
```
cd
```

Change current working directory to the specified path
```
cd [path]
```

Print working directory
```
pwd
```

## Listing files
List files in current directory
```
ls [options...]
```

`-a` or `--all`: Include entries starting with `.`

`-l`: Use a long listing format

## Vim text editor
Improved version of Vi text editor

VIM - Vi IMproved

Vim official site: https://www.vim.org/

Vim is an advanced and highly configurable text editor built to enable efficient text editing.

### Using Vim
Open Vim
```
vi
vim
```

Edit specific files
```
vi [file...]
vim [file...]
```

### Commands

Vim Cheat Sheet: https://vim.rtorr.com/

#### Cursor movement
`h` - Move cursor left

`j` - Move cursor down

`k` - Move cursor up

`l` - Move cursor right

`H` - Move to top of screen

`M` - Move to middle of screen

`L` - Move to bottom of screen

#### Saving and exiting

`:w` - Save file

`:wq` or `:x` or `ZZ` - Save and exit

`:q` - Exit, fails if there are unsaved changes

`:q!` or `ZQ` - Exit and throw away unsaved changes