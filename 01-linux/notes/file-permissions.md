In Linux file permissions, **rwx** stands for:

| Permission | Meaning | For a File                       | For a Directory              |
| ---------- | ------- | -------------------------------- | ---------------------------- |
| **r**      | Read    | View file contents               | List files inside (`ls`)     |
| **w**      | Write   | Modify the file                  | Create, delete, rename files |
| **x**      | Execute | Run the file as a program/script | Enter the directory (`cd`)   |

Example:

`- rwxr-xr--`

Break it down:

`- rwx r-x r--`

       │   │     │

       │   │     └── Others Rights

      │   └────── Group Rights

      └────────── Owner Rights

- **Owner:** `rwx` = read, write, execute
- **Group:** `r-x` = read, execute
- **Others:** `r--` = read only

As a beginner, remember:

- **r** = look at it 👀
- **w** = change it ✏️
- **x** = use/run it ▶️

**Binary, Octal and String Representation!**

When learning Linux permissions, you'll often see **three representations of the same permissions**:

| String | Binary | Octal |
| ------ | ------ | ----- |
| `rwx`  | 111    | 7     |
| `rw-`  | 110    | 6     |
| `r-x`  | 101    | 5     |
| `r--`  | 100    | 4     |
| `-wx`  | 011    | 3     |
| `-w-`  | 010    | 2     |
| `--x`  | 001    | 1     |
| `---`  | 000    | 0     |

### How it works

Each permission has a binary value:

r = 4 = 100

w = 2 = 010

x = 1 = 001

Add the values together:

Plain Text

rwx = 4 + 2 + 1 = 7

rw- = 4 + 2 + 0 = 6

r-x = 4 + 0 + 1 = 5

r-- = 4 + 0 + 0 = 4

### Example: 755

`chmod 755 myscript.sh`

Break down `755`:

7 = `rwx` = owner

5 = `r-x`= group

5 =`r-x`= others

So:

`rwxr-xr-x`

An **Octal (chmod) Calculator** helps you convert between permission strings (`rwxr-xr-x`) and the numeric values used by `chmod` (`755`).

Adding and removing permissions:

`chmod u+x,g+r,o-w example.txt` changes permissions for the file ‘example.txt’:

- `u+x` → give the **user (owner)** execute permission.
- `g+r` → give the **group** read permission.
- `o+w` → give **others** write permission.

Grouping Permissions Using Symbolic Operators:

`chmod ug=rw,o=r example.txt` **sets exact permissions**:

- `ug=rw` → User (owner) and Group get **read and write** permissions only.
- `o=r` → Others get **read** permission only.

As a Linux shortcut, remember:

`+` = add permission

`-` = remove permission

`=` = set exact permission

`u` = user (owner)

`g` = group

`o` = others

`a` = all

`chmod` stands for **change mode**.

`chown` stands for **change owner**.

`chgrp` stands for **change group**. It changes the group ownership of a file or directory.
