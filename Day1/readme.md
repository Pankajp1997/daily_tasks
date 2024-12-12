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


