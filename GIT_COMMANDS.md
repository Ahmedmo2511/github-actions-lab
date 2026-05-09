# All Git Commands Needed - Copy & Paste Ready

## 📋 Complete Command Reference

Copy and paste these commands in order as you follow the beginner guide.

---

## EXERCISE 1: FIRST PUSH

### Step 1: Initialize Repository
```bash
cd C:\Users\DELL\OneDrive\Desktop\Agile\github-actions-lab
```

### Step 2: Initialize Git
```bash
git init
```

### Step 3: Configure Git (First Time Only)
Replace "Your Name" and "your@email.com" with your actual info:
```bash
git config user.name "Your Name"
git config user.email "your@email.com"
```

Example:
```bash
git config user.name "John Smith"
git config user.email "john@gmail.com"
```

### Step 4: Check Files
```bash
git status
```

### Step 5: Add All Files
```bash
git add .
```

### Step 6: Create First Commit
```bash
git commit -m "Initial commit: Add GitHub Actions lab exercises"
```

### Step 7: Add Remote Repository
Replace `YOUR_USERNAME` with your GitHub username:
```bash
git remote add origin https://github.com/YOUR_USERNAME/github-actions-lab.git
```

Example:
```bash
git remote add origin https://github.com/johndoe/github-actions-lab.git
```

### Step 8: Rename Branch to Main
```bash
git branch -M main
```

### Step 9: Push to GitHub
```bash
git push -u origin main
```

✅ **Exercise 1 Complete - Check GitHub Actions tab for workflow run!**

---

## EXERCISE 2: BRANCHING & PR

### Step 1: Create Dev Branch
```bash
git checkout -b dev
```

Or use new syntax:
```bash
git switch -c dev
```

### Step 2: Verify You're on Dev
```bash
git branch
```

Should show:
```
  main
* dev
```

### Step 3: Push Dev Branch
```bash
git push -u origin dev
```

### Step 4: Make a Change (Optional)
```bash
echo "Testing dev branch" >> test.txt
```

### Step 5: Add and Commit
```bash
git add .
git commit -m "Update test file on dev branch"
```

### Step 6: Push Changes
```bash
git push origin dev
```

✅ **Workflow should now run! Check Actions tab.**

### Step 7: Create Pull Request
⚠️ Do this on GitHub website:
1. Go to your repository: https://github.com/YOUR_USERNAME/github-actions-lab
2. Click "Pull requests" tab
3. Click "New pull request"
4. Base: main, Compare: dev
5. Click "Create pull request"

### Step 8: Wait for Status Checks
Watch the PR page for green checkmarks.

### Step 9: Merge the PR
On GitHub:
1. Click "Merge pull request"
2. Click "Confirm merge"

### Step 10: Sync Local Repo
```bash
git checkout main
git pull origin main
```

✅ **Exercise 2 Complete!**

---

## EXERCISE 3: PYTHON WORKFLOW

### Step 1: Recreate Dev Branch
```bash
git checkout -b dev
git push -u origin dev
```

### Step 2: Trigger Advanced Workflow
```bash
echo "Testing Exercise 3" >> exercise3.txt
git add .
git commit -m "Trigger Exercise 3 advanced workflow"
git push origin dev
```

✅ **Watch Actions tab - Exercise 3 workflow should run!**

### Step 3: Create Another Pull Request
On GitHub:
1. Go to Pull requests
2. New pull request (dev → main)
3. Create pull request
4. Wait for checks

### Step 4: Merge Final PR
```bash
git checkout main
git pull origin main
```

✅ **Exercise 3 Complete!**

---

## USEFUL COMMANDS DURING DEVELOPMENT

### Check Status Anytime
```bash
git status
```

### See Commit History
```bash
git log --oneline
```

### See All Branches
```bash
git branch -a
```

### Switch Between Branches
```bash
git checkout main
git checkout dev
```

Or newer syntax:
```bash
git switch main
git switch dev
```

### Undo Last Commit (Keep Changes)
```bash
git reset HEAD~1
```

### Undo Last Commit (Delete Changes)
```bash
git reset --hard HEAD~1
```

### View What Changed in Last Commit
```bash
git show
```

### Compare Two Branches
```bash
git diff main dev
```

---

## BRANCH MANAGEMENT COMMANDS

### Delete Local Branch
```bash
git branch -d dev
```

### Delete Remote Branch
```bash
git push origin --delete dev
```

### Rename Current Branch
```bash
git branch -m new-name
```

### Create Branch from Main
```bash
git checkout main
git pull origin main
git checkout -b new-feature
```

### List Remote Branches
```bash
git branch -r
```

---

## TROUBLESHOOTING COMMANDS

### View Remote URL
```bash
git remote -v
```

Should show:
```
origin  https://github.com/YOUR_USERNAME/github-actions-lab.git (fetch)
origin  https://github.com/YOUR_USERNAME/github-actions-lab.git (push)
```

### Check Current Branch
```bash
git branch
```

### Verify Git Configuration
```bash
git config --global user.name
git config --global user.email
```

### See Last 5 Commits
```bash
git log -5 --oneline
```

### Reset to Remote State
```bash
git fetch origin
git reset --hard origin/main
```

### Force Push (Use with Caution!)
```bash
git push -f origin branch-name
```

---

## COMPLETE COMMAND SEQUENCE (COPY-PASTE READY)

### First Time Setup Only:
```bash
cd C:\Users\DELL\OneDrive\Desktop\Agile\github-actions-lab
git init
git config user.name "Your Name"
git config user.email "your@email.com"
git add .
git commit -m "Initial commit: Add GitHub Actions lab exercises"
git remote add origin https://github.com/YOUR_USERNAME/github-actions-lab.git
git branch -M main
git push -u origin main
```

### Exercise 2 - Create Dev Branch:
```bash
git checkout -b dev
git push -u origin dev
echo "Exercise 2 changes" >> notes.txt
git add .
git commit -m "Add Exercise 2 workflow"
git push origin dev
git checkout main
git pull origin main
```

### Exercise 3 - Continue Dev Work:
```bash
git checkout dev
echo "Exercise 3 changes" >> notes.txt
git add .
git commit -m "Add Exercise 3 workflow"
git push origin dev
git checkout main
git pull origin main
```

---

## WINDOWS POWERSHELL SPECIFIC NOTES

### If you get "permission denied":
Right-click PowerShell and select "Run as administrator"

### File path tip:
Windows uses backslashes: `C:\Users\...`
Git uses forward slashes: `/c/Users/...`
You can use either - PowerShell handles both

### Paste in PowerShell:
- Right-click and select "Paste"
- Or use `Ctrl + V` (may not work in some versions)

### Clear Screen:
```bash
Clear-Host
```

Or shorter:
```bash
cls
```

---

## GITHUB CREDENTIALS

### First Time on New Computer:
You may be prompted to authenticate. Choose:
- HTTPS: Use GitHub Personal Access Token (PAT)
- SSH: Use SSH keys

### Creating a Personal Access Token:
1. Go to https://github.com/settings/tokens
2. Click "Generate new token"
3. Select "repo" scope
4. Copy the token
5. Use token as password when pushing

### Windows Credential Manager:
If you're asked for password, update your credentials:
1. Open Control Panel
2. Search "Credential Manager"
3. Click "Windows Credentials"
4. Find git entry and update

---

## SCRIPT TO AUTOMATE SETUP (Optional)

Save this as `setup.ps1` and run:
```bash
./setup.ps1
```

---

```powershell
# setup.ps1 - Automated setup script

$projectPath = "C:\Users\DELL\OneDrive\Desktop\Agile\github-actions-lab"
$username = "Your-GitHub-Username"

cd $projectPath

Write-Host "Initializing Git repository..." -ForegroundColor Green
git init

Write-Host "Configuring Git..." -ForegroundColor Green
git config user.name "Your Name"
git config user.email "your@email.com"

Write-Host "Adding files..." -ForegroundColor Green
git add .

Write-Host "Creating initial commit..." -ForegroundColor Green
git commit -m "Initial commit: Add GitHub Actions lab exercises"

Write-Host "Adding remote repository..." -ForegroundColor Green
git remote add origin "https://github.com/$username/github-actions-lab.git"

Write-Host "Setting main branch..." -ForegroundColor Green
git branch -M main

Write-Host "Pushing to GitHub..." -ForegroundColor Green
git push -u origin main

Write-Host "Setup complete!" -ForegroundColor Green
```

---

## SUMMARY

**Remember**: 
- 📁 Always be in the right directory
- 🔀 Know which branch you're on: `git branch`
- 📤 Push after every commit: `git push origin branch-name`
- ✅ Verify on GitHub after pushing
- 🔍 Check Actions tab for workflow runs

**Most Common Sequence**:
```bash
git add .
git commit -m "Description"
git push origin branch-name
```

That's it! These three commands are 95% of what you'll use. 🚀

