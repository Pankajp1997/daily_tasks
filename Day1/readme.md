Day 1. Setting Up GitHub SSH Key Authentication

It is always recommended to use the ssh-key authentication for the repository access from the terminal. 
It is very heactic task always to enter the github token when need to use the token. 
We are following the below workarounds to enable ssh authentication. 
Step 1: Generate an SSH Key Pair

Open a terminal on your system.

Generate an SSH key pair by running:

ssh-keygen -t ed25519 -C "your_email@example.com"

Replace your_email@example.com with the email address associated with your GitHub account.

When prompted:

Press Enter to save the key in the default location (e.g., ~/.ssh/id_ed25519).

Enter a passphrase (optional) for extra security, or leave it blank for convenience.


Step 2: Add the SSH Key to the SSH Agent

Start the SSH agent:
eval "$(ssh-agent -s)"

Add your SSH private key to the agent:

ssh-add ~/.ssh/id_ed25519

Step 3: Add the SSH Public Key to Your GitHub Account

Retrieve your public key:

cat ~/.ssh/id_ed25519.pub

Copy the output.

Go to GitHub:

Log in to your GitHub account.

Navigate to Settings > SSH and GPG keys.

Click New SSH Key.

Add the SSH Key:

Provide a title for the key (e.g., "My Laptop SSH Key").

Paste the public key into the text box.

Click Add SSH Key.

Step 4: Test the SSH Connection

Verify the SSH connection to GitHub:

ssh -T git@github.com

You should see a message like:

Hi username! You've successfully authenticated, but GitHub does not provide shell access.

Step 5: Update Your Git Remote to Use SSH

Check the current remote URL of your repository:

git remote -v

Update the remote to use SSH:

git remote set-url origin git@github.com:your-username/your-repository.git

Replace your-username and your-repository with your GitHub username and repository name.


