# Git & GitHub Setup – My First Drill

Today I completed my initial Git and GitHub setup.

First, I created my GitHub account with a professional username.

Then I configured Git on my Mac:
- Set global username
- Set global email
- Verified Git installation

After that, I generated an SSH key using ed25519 and added the public key to my GitHub account.

I tested the SSH connection using:
ssh -T git@github.com

It successfully authenticated.

Important learning:
Git should be initialized in the course repository root, not inside each module folder.



Shell Basics — My Notes
Overview

The shell is my primary interface to interact with my system.
It allows me to:

Navigate directories

Create, move, copy, and delete files

View and search inside text files

Combine commands using pipes and redirection

Customize my workflow using aliases

These are foundational skills for daily development work.

1️⃣ Navigation Commands
pwd — Print Working Directory

Shows my current location in the filesystem.

pwd


Useful to verify where I am before performing file operations.

ls — List Files

Shows contents of a directory.

ls

Important flags:

-l → Long format (permissions, owner, size, date)

-a → Show hidden files

-la → Long format + hidden files

Example:

ls -la


Hidden files start with . (like .zshrc, .git).

cd — Change Directory

Moves between folders.

cd foldername

Special paths:

. → current directory

.. → parent directory

~ → home directory

cd - → previous directory

2️⃣ File & Folder Management
mkdir — Create Folder
mkdir foldername


Create nested folders:

mkdir -p a/b/c


-p creates parent directories if they don’t exist.

rm — Remove File
rm file.txt


Remove directory:

rm -r foldername


⚠️ -r means recursive. Be careful.

rm -rf is dangerous because:

-r = recursive

-f = force (no confirmation)

cp — Copy File
cp file1.txt file2.txt


Copy folder:

cp -r folder1 folder2

mv — Move or Rename

Rename:

mv old.txt new.txt


Move:

mv file.txt folder/


mv changes file location or name.

3️⃣ Viewing File Content
cat

Prints entire file content.

cat file.txt


Not suitable for very large files.

less

Scrollable file viewer.

less file.txt


Controls:

q → quit

/word → search

g → top

Shift+g → bottom

Better for large files.

head

Shows first 10 lines by default.

head file.txt


Custom number of lines:

head -n 5 file.txt

tail

Shows last 10 lines.

tail file.txt


Live monitoring:

tail -f file.txt


-f = follow (used for logs).

wc — Word Count
wc file.txt


Shows:

lines

words

bytes

Specific flags:

wc -l file.txt   # count lines
wc -w file.txt   # count words
wc -c file.txt   # count bytes

4️⃣ Searching Text — grep

Searches for patterns in text.

grep "error" file.txt

Useful flags:

-i → case insensitive

-n → show line numbers

-r → recursive search

-v → invert match (show non-matching lines)

-c → count matches

Example:

grep -r "functionName" .


Search entire project directory.

5️⃣ Pipes (|)

Pipe connects output of one command to input of another.

Example:

ls | wc -l


Count number of files.

Another example:

grep error log.txt | wc -l


Count number of error lines.

Pipe allows command chaining.

6️⃣ Redirection

Controls where output goes.

> Overwrite
echo "hello" > file.txt


Creates or overwrites file.

>> Append
echo "world" >> file.txt


Adds to existing file without overwriting.

7️⃣ Shell History

View previous commands:

history


Search previous commands:

Press:

Ctrl + R


This helps avoid retyping long commands.

8️⃣ Shell Configuration — .zshrc

My shell configuration file is:

~/.zshrc


It runs every time I open the terminal.

Creating an Alias

Example:

alias ll="ls -la"


Reload shell:

source ~/.zshrc


Now I can type:

ll