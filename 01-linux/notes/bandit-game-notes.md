## Bandit Level 0 → Level 1

**Challenge:**

The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

**Solution:**

```bash
ls
ls -l
cat readme
```

**Explanation:**

I first used the `ls` command in the terminal and saw a file called readme. Next, I ran `ls -l`, which displayed the permissions -rw-r-----. The leading - indicated that it was a regular file rather than a directory, which would begin with d. I then used the command `cat readme` to view the file's contents, and it revealed the password needed to complete Bandit Level 2.

**Password:** [6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR]

**What I learned:**

In this level, I learned how to list files using `ls`, view detailed file information with `ls -l`, identify a regular file from its permissions (-rw-r-----), and use `cat` to read the contents of a file. These commands allowed me to locate and retrieve the password for the next Bandit level.

## Bandit Level 1 → Level 2

**Challenge:**

The password for the next level is stored in a file called - located in the home directory

**Solution:**

```bash
ls
ls -l
cat ./-
```

**Explanation:**

I first used the ls command to list the files in my home directory and saw a file named -. Next, I ran ls -l to view more details about the file and confirm that it was a regular file, indicated by the leading - in the permissions string (-rw-r-----). Because - is a special character that is often interpreted as standard input, I could not use cat - directly. Instead, I used cat ./-, where ./ specifies the current directory and allows the filename to be treated literally. This displayed the contents of the file, which contained the password for the next level.

**Password:** [PK8fYLZg2hnHSz83plBL1iEPKdD3QToB]

**What I learned:**

How to use ls to list files in a directory.
How to use ls -l to view detailed file information and permissions.
That the first character in a permissions string indicates the file type (- for a regular file and d for a directory).
That some filenames can contain special characters, such as -, which may be interpreted differently by commands.
How to reference a file with a special name using ./filename.
How to use cat to display the contents of a file.

Key takeaway: Special characters in filenames can cause commands to behave differently, so it's important to know how to explicitly reference files when needed.
