🧠 GIT ZERO TO HERO — My Hands-on Journey with Git and GitHub
📘 Objective

This repository documents every command I used and the concepts I learned while setting up and pushing my first GitHub repository from an EC2 instance using the Linux terminal.

⚙️ Step 1: Installing Git
apt update
apt install git -y
git -v


✅ Explanation:

apt update updates package indexes.

apt install git -y installs Git without confirmation prompts.

git -v verifies Git installation.

📁 Step 2: Creating a Project Directory
mkdir projects
cd projects/


✅ Explanation:

Created a directory called projects to keep all repositories organized.

cd is used to navigate inside the folder.

🧰 Step 3: Initializing Git Repository
git init


✅ Explanation:
This command initializes a new empty Git repository inside the folder by creating a hidden .git/ directory that stores version history and configurations.

🔐 Step 4: Setting Up SSH Key for GitHub Access
ssh-keygen
cat /root/.ssh/id_ed25519.pub


✅ Explanation:

ssh-keygen generates a new SSH key pair.

The .pub file contains the public key — you must copy this key and add it to your GitHub account under
Settings → SSH and GPG Keys → New SSH Key.

🧪 Step 5: Testing SSH Connection
ssh -T git@github.com


✅ Expected Output:

Hi ANUP-2023! You've successfully authenticated, but GitHub does not provide shell access.


✅ Meaning:
Your EC2 instance is now securely connected to GitHub via SSH.

📄 Step 6: Creating README File
echo "# github_actions" >> README.md


✅ Explanation:
Creates a README file with a project title.
You can open and edit it using any editor (e.g., nano README.md).

🧩 Step 7: Tracking Files and Making First Commit
git status
git add README.md
git commit -m "first commit"


✅ Explanation:

git status shows untracked and staged files.

git add moves files into the staging area.

git commit -m saves them permanently with a message.

🌿 Step 8: Creating & Renaming Branch
git branch -M master


✅ Explanation:
Renames the current branch to master (or main, depending on your preference).

🌐 Step 9: Linking Local Repo to Remote Repo on GitHub
git remote add origin git@github.com:ANUP-2023/github_actions.git
git remote -v


✅ Explanation:

origin is an alias pointing to your GitHub repository.

git remote -v verifies the link.

☁️ Step 10: Pushing Local Code to GitHub
git push -u origin master


✅ Explanation:
Uploads all committed changes from local to GitHub for the first time.

💡 Step 11: Cloning Another Repository and Replacing Code
git clone https://github.com/LondheShubham153/tws-portfolio.git
mv ./tws-portfolio/* .
rm -rvf tws-portfolio/


✅ Explanation:

Cloned someone else’s repository for learning.

Moved its files into your local repo folder and deleted the clone folder.

📦 Step 12: Committing and Pushing Imported Code
git add .
git commit -m "Added code from public repository"
git push


✅ Explanation:
Tracked and pushed all the imported files to GitHub.

🧍 Step 13: Fixing Commit Author Name
git config --global user.name "ANUP KUMAR"
git config --global user.email "your_email@example.com"
git commit --amend --reset-author
git push -u origin master


✅ Explanation:

Updated the global user identity for commits.

Amended the previous commit to correct author details.

🔄 Step 14: Pulling Remote Changes Before Push
git pull --rebase origin master


✅ Explanation:
Used when remote repository has commits not yet in local — ensures your history remains clean.

🚀 Step 15: Final Push
git push origin master --force


✅ Explanation:
Used to overwrite the remote branch (only when necessary).

📜 Step 16: Verifying Repository
git status
git log --oneline


✅ Explanation:
Checks that your working directory is clean and all commits are visible.

🎯 Summary
Step	Concept	Command	Purpose
1	Install Git	apt install git	Install Git on EC2
2	Initialize Repo	git init	Start local repository
3	Add SSH Key	ssh-keygen	Secure connection
4	Commit Changes	git commit	Save changes
5	Push to GitHub	git push	Upload code
🌟 Result

✅ Successfully created and pushed my first repository from an EC2 instance to GitHub using SSH authentication.
Now, I can manage all my projects directly from my EC2 terminal or VS Code connected to the instance.
