
# Docker Project
## Installation Steps
### Step 1: Update Packages


![Docker Logo](https://www.docker.com/app/uploads/2021/11/container-what-is-container-1110x961.png)

sudo apt update
sudo apt install git -y
git --version

# 🚀 Git Commands Practice on EC2

This repository documents all the steps I followed to set up **Git** on an **AWS EC2 instance**, configure **SSH access** to GitHub, clone a public repository, and push code to my own GitHub repo.

---

## 🧩 Step 1: Install Git

```bash
sudo apt update
sudo apt install git -y
git --version

📁 Step 2: Initialize a Local Repository
mkdir projects
cd projects
git init

🔑 Step 3: Generate SSH Key & Connect to GitHub
ssh-keygen
cat ~/.ssh/id_ed25519.pub


Add this key to GitHub:

GitHub → Settings → SSH and GPG Keys → New SSH Key → Paste the key → Save

Test connection:

ssh -T git@github.com


✅ Expected Output:

Hi username! You've successfully authenticated.

📝 Step 4: Create README File and First Commit
echo "# github_actions" >> README.md
git add README.md
git commit -m "first commit"

🌿 Step 5: Set Branch to Master
git branch -M master

🔗 Step 6: Connect to Remote GitHub Repository
git remote add origin git@github.com:ANUP-2023/github_actions.git
git remote -v

📤 Step 7: Push Local Code to GitHub
git push -u origin master


💡 If you see a “non-fast-forward” error:

git pull --rebase origin master
git push -u origin master

📥 Step 8: Clone Public Repository and Merge Code
git clone https://github.com/LondheShubham153/tws-portfolio.git
mv ./tws-portfolio/* .
rm -rf tws-portfolio/
git add .
git commit -m "Added code from public repository"
git push -u origin master

⚙️ Step 9: Configure Git Identity
git config --global user.name "ANUP KUMAR"
git config --global user.email "your_email@example.com"
git config --global --list


If commits still show as root, fix author info:

git commit --amend --reset-author
git push --force

🧠 Step 10: Common Git Commands
Command	Description
git status	Check current file status
git add .	Stage all changes
git commit -m "message"	Commit staged changes
git log	View commit history
git remote -v	Show remote repositories
git pull	Fetch and merge changes
git push	Push commits to remote
✅ Summary

This project demonstrates:

Installing and configuring Git on EC2

Connecting to GitHub using SSH keys

Initializing and pushing a repo to GitHub

Cloning public repos and merging them

Managing Git commits and author info

