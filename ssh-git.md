Setting Up SSH for Git (GitHub, GitLab, etc.)
If you want to authenticate with GitHub, GitLab, or any Git server using SSH, follow these steps:

Step 1: Generate an SSH Key (If You Don’t Have One)
Run this command to create a new SSH key (if you don’t have one already):

```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

```
Press Enter to accept the default file location (~/.ssh/id_rsa).
Optionally, add a passphrase for extra security.
Step 2: Start the SSH Agent
Run:

```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa

```
Step 3: Add the SSH Key to GitHub/GitLab
Copy your public key to the clipboard:

``` 
cat ~/.ssh/id_rsa.pub

```
Go to GitHub/GitLab settings → SSH keys.
Paste the key and save it.
