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


<<<<<<< HEAD
Checking branch again
=======
Checking branch again

Revision
>>>>>>> branch-test
