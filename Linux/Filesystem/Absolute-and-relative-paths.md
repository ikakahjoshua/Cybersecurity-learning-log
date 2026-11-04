# Absolute and Relative Paths

## Objective

To understand absolute and relative paths in Linux, how they work, their differences, and how to use them when navigating the filesystem and accessing files and directories.

## Commands Used

| Command | Description |
|---|---|
| `pwd` | Displays the current working directory. |
| `cd` | Changes the current working directory. |
| `ls` | Lists files and directories. |
| `cat` | Displays the contents of a file. |
| `mkdir` | Creates directories. |
| `touch` | Creates empty files. |
| `realpath` | Displays the absolute path of a file or directory. |

## Observations

### 1. Absolute Paths

An absolute path specifies the complete location of a file or directory, starting from the root directory `/`.

It does not depend on the current working directory.

Example:

`/home/kali/Documents/report.txt`

Regardless of the current working directory, this path points to the same location.

### 2. Relative Paths

A relative path specifies the location of a file or directory in relation to the current working directory.

Unlike absolute paths, relative paths depend on where you are currently located.

For example, if my current working directory is:

`/home/kali`

I can access a file inside Documents using:

`cat Documents/report.txt`

Linux resolves the path relative to `/home/kali`.

### 3. Special Path References

Linux provides special references that make navigation easier.

- `.` represents the current directory.
- `..` represents the parent directory.
- `~` represents the current user's home directory.

Examples:

`cd .` — Remains in the current directory.

`cd ..` — Moves one directory level upward.

`cd ../..` — Moves two directory levels upward.

`cd ~` — Moves to the user's home directory.

### 4. Differences Between Absolute and Relative Paths

| Absolute Path | Relative Path |
|---|---|
| Starts from `/`. | Starts from the current working directory. |
| Does not depend on the current working directory. | Depends on the current working directory. |
| Specifies the complete location. | Specifies the location relative to the current directory. |
| Example: `/home/kali/Documents/file.txt` | Example: `Documents/file.txt` |

Both paths can point to the same file or directory.

## Practical Experiments

### 1. Creating a directory structure

```bash
mkdir -p ~/path-lab/{Documents,Downloads,Projects}

Create some empty files:
touch ~/path-lab/Documents/report.txt
touch ~/path-lab/Downloads/notes.txt
touch ~/path-lab/Projects/script.sh
2. Checking the current working directory
cd ~/path-lab/Documents
pwd
3. Accessing a file using an absolute path
cat ~/path-lab/Documents/report.txt
4. Accessing a file using a relative path
cat ../Downloads/notes.txt
5. Navigating using relative paths
cd ../Projects
pwd
6. Exploring special path references
cd .
cd ..
cd ../..
cd ~
7. Resolving a relative path into an absolute path
realpath ~/path-lab/Documents/report.txt

## Screenshots



