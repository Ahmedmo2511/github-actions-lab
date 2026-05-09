# Beginner-Friendly Step-by-Step Guide

## ✅ COMPLETE CHECKLIST FOR EXERCISES

This guide walks through every single step with explanations.

---

# EXERCISE 1: YOUR FIRST GITHUB ACTIONS WORKFLOW

## Goal: 
Make a workflow that prints "Hello from GitHub Actions!" whenever you push code.

---

## STEP 1️⃣: Open PowerShell/Terminal

**What to do:**
- Press `Win + X` on your keyboard
- Click "Windows PowerShell" or "Terminal"
- A black window will open

**What you should see:**
```
PS C:\Users\YourName>
```

---

## STEP 2️⃣: Navigate to Your Project Folder

**What to do:**
Type this command and press Enter:
```bash
cd "C:\Users\DELL\OneDrive\Desktop\Agile\github-actions-lab"
```

**What you should see:**
```
PS C:\Users\DELL\OneDrive\Desktop\Agile\github-actions-lab>
```

---

## STEP 3️⃣: Initialize Git Repository

**What to do:**
Type this command and press Enter:
```bash
git init
```

**What you should see:**
```
Initialized empty Git repository in C:\Users\DELL\OneDrive\Desktop\Agile\github-actions-lab\.git\
```

---

## STEP 4️⃣: Configure Git (First Time Only)

**What to do:**
Type these commands (replace the values):

```bash
git config user.name "Your Full Name"
git config user.email "youremail@example.com"
```

**Example:**
```bash
git config user.name "John Smith"
git config user.email "john.smith@gmail.com"
```

**What you should see:**
No output means it worked!

---

## STEP 5️⃣: Check Project Files

**What to do:**
Type this command and press Enter:
```bash
ls -la
```

**What you should see:**
```
Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d----          5/9/2026   1:00 PM                .git
d----          5/9/2026   1:00 PM                .github
-a---          5/9/2026   1:00 PM          1234  README.md
-a---          5/9/2026   1:00 PM          2345  YAML_REFERENCE.md
```

---

## STEP 6️⃣: Verify Workflow Files Exist

**What to do:**
Type this command and press Enter:
```bash
ls -la .github/workflows/
```

**What you should see:**
```
Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---          5/9/2026   1:00 PM           234   advanced.yml
-a---          5/9/2026   1:00 PM           198   dev-branch.yml
-a---          5/9/2026   1:00 PM           156   hello.yml
```

✅ **All three files are there!**

---

## STEP 7️⃣: Add All Files to Git

**What to do:**
Type this command and press Enter:
```bash
git add .
```

**What you should see:**
No output means it worked!

---

## STEP 8️⃣: Check Git Status

**What to do:**
Type this command and press Enter:
```bash
git status
```

**What you should see:**
```
On branch main

No commits yet

Changes to be committed:
  new file:   .github/workflows/hello.yml
  new file:   .github/workflows/dev-branch.yml
  new file:   .github/workflows/advanced.yml
  new file:   README.md
  new file:   YAML_REFERENCE.md
  new file:   GITHUB_UI_GUIDE.md
```

---

## STEP 9️⃣: Commit Your Files

**What to do:**
Type this command and press Enter:
```bash
git commit -m "Initial commit: Add GitHub Actions lab exercises"
```

**What you should see:**
```
[main (root-commit) abc1234] Initial commit: Add GitHub Actions lab exercises
 6 files changed, 450 insertions(+)
 create mode 100644 .github/workflows/hello.yml
 create mode 100644 .github/workflows/dev-branch.yml
 create mode 100644 .github/workflows/advanced.yml
 create mode 100644 README.md
 create mode 100644 YAML_REFERENCE.md
 create mode 100644 GITHUB_UI_GUIDE.md
```

---

## STEP 🔟: Create Repository on GitHub

**What to do:**
1. Go to https://github.com (sign in if needed)
2. Click the `+` icon in top-right corner
3. Click "New repository"
4. Fill in:
   - **Repository name**: `github-actions-lab`
   - **Description**: "GitHub Actions learning exercises"
   - **Visibility**: ✓ Public (required for free GitHub Actions)
   - Leave other options as default
5. Click "Create repository"

**What you should see:**
A page with:
- Your new repository name
- Quick setup instructions
- Commands to push existing code

**⚠️ IMPORTANT**: Don't click anything yet! Copy the commands shown on this page.

---

## STEP 1️⃣1️⃣: Add Remote Repository

**What to do:**
On the GitHub page you just opened, you'll see a section that says:
```
…or push an existing repository from the command line
```

Copy the first command that looks like:
```bash
git remote add origin https://github.com/YOUR_USERNAME/github-actions-lab.git
```

**Type it in PowerShell and press Enter:**
```bash
git remote add origin https://github.com/YOUR_USERNAME/github-actions-lab.git
```

(Replace `YOUR_USERNAME` with your actual GitHub username)

**What you should see:**
No output means it worked!

---

## STEP 1️⃣2️⃣: Set Main Branch

**What to do:**
Type this command and press Enter:
```bash
git branch -M main
```

**What you should see:**
No output means it worked!

---

## STEP 1️⃣3️⃣: Push to GitHub

**What to do:**
Type this command and press Enter:
```bash
git push -u origin main
```

**What you should see:**
```
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 8 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (7/7), 1.23 KiB | 615.00 KiB/s, done.
Total 7 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/YOUR_USERNAME/github-actions-lab.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
```

✅ **Your code is on GitHub!**

---

## STEP 1️⃣4️⃣: See Your First Workflow Run

**What to do:**
1. Go to your GitHub repository
2. Click the **"Actions"** tab at the top
3. You should see "Exercise 1 - Hello GitHub Actions" in the left sidebar
4. Click on it
5. Click on the run (it should show with a timestamp)
6. You'll see the job and steps

**What you should see:**
- Green checkmark ✅ next to the job
- Status: "Completed successfully"

---

## STEP 1️⃣5️⃣: View the Workflow Output

**What to do:**
1. In the same page, click the step called **"Print Hello Message"**
2. The step will expand showing the output

**What you should see:**
```
Run echo "Hello from GitHub Actions!"
Hello from GitHub Actions!
```

🎉 **EXERCISE 1 COMPLETE!**

---

# EXERCISE 2: BRANCHING & PULL REQUESTS

## Goal:
Create a dev branch, trigger workflows on dev pushes, and practice pull requests.

---

## STEP 1️⃣: Create Dev Branch Locally

**What to do:**
In PowerShell, type this command and press Enter:
```bash
git checkout -b dev
```

(Or use the newer syntax:)
```bash
git switch -c dev
```

**What you should see:**
```
Switched to a new branch 'dev'
```

---

## STEP 2️⃣: Verify You're on Dev Branch

**What to do:**
Type this command and press Enter:
```bash
git branch
```

**What you should see:**
```
  main
* dev
```

The `*` shows you're on `dev` branch.

---

## STEP 3️⃣: Push Dev Branch to GitHub

**What to do:**
Type this command and press Enter:
```bash
git push -u origin dev
```

**What you should see:**
```
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
remote: 
remote: Create a pull request for 'dev' by visiting:
remote:   https://github.com/YOUR_USERNAME/github-actions-lab/pull/new/dev
remote:
To https://github.com/YOUR_USERNAME/github-actions-lab.git
 * [new branch]      dev -> dev
Branch 'dev' set up to track remote branch 'origin/dev' from 'origin'.
```

✅ **Dev branch is on GitHub!**

---

## STEP 4️⃣: Make a Change on Dev Branch

**What to do:**
Create a new file or modify existing. For example:
```bash
echo "This is dev branch" >> notes.txt
```

Then add and commit:
```bash
git add .
git commit -m "Update notes on dev branch"
git push origin dev
```

**What you should see:**
```
[dev abc5678] Update notes on dev branch
```

---

## STEP 5️⃣: Check Workflow Ran

**What to do:**
1. Go to GitHub Actions tab
2. Look for a new run of "Exercise 2 - Dev Branch & Pull Requests"
3. Click on it
4. View the logs

**What you should see:**
- Workflow triggered by "push"
- Branch: "dev"
- Event: "push"

---

## STEP 6️⃣: Create Pull Request on GitHub

**What to do:**
1. Go to your GitHub repository
2. Click **"Pull requests"** tab
3. Click **"New pull request"** button
4. Select:
   - **Base**: `main` (the target)
   - **Compare**: `dev` (the source)
5. Click **"Create pull request"**
6. Add title: "Merge dev to main for Exercise 2"
7. Click **"Create pull request"** again

**What you should see:**
- PR shows files changed
- A "Checks" section appears

---

## STEP 7️⃣: Wait for Workflow to Complete

**What to do:**
1. On the same PR page, scroll down to see "Checks"
2. Wait for the workflow to show a checkmark
3. It might show as yellow (running) first

**What you should see:**
After a few seconds:
- Green checkmark next to "Exercise 2"
- Status: "All checks passed"

---

## STEP 8️⃣: Merge the Pull Request

**What to do:**
1. On the PR page, click **"Merge pull request"**
2. Click **"Confirm merge"**
3. Optionally click "Delete branch" (we'll recreate it)

**What you should see:**
```
Pull request successfully merged and closed
```

---

## STEP 9️⃣: Sync Local Repository

**What to do:**
In PowerShell, type these commands:

```bash
git checkout main
git pull origin main
```

**What you should see:**
```
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
Updating abc5678..def9012
Fast-forward
 notes.txt | 1 +
 1 file changed, 1 insertion(+)
```

🎉 **EXERCISE 2 COMPLETE!**

---

# EXERCISE 3: ADVANCED PYTHON WORKFLOW

## Goal:
Use Python 3.10, run scripts, and install packages in a workflow.

---

## STEP 1️⃣: Recreate Dev Branch

**What to do:**
Type this command and press Enter:
```bash
git checkout -b dev
```

**What you should see:**
```
Switched to a new branch 'dev'
```

---

## STEP 2️⃣: Push to Dev Again

**What to do:**
```bash
git push -u origin dev
```

**What you should see:**
Dev branch is set up to track remote branch.

---

## STEP 3️⃣: Trigger the Advanced Workflow

**What to do:**
Make a small change and push:
```bash
echo "Testing Exercise 3" >> test.txt
git add .
git commit -m "Trigger Exercise 3 workflow"
git push origin dev
```

**What you should see:**
```
[dev ghi3456] Trigger Exercise 3 workflow
```

---

## STEP 4️⃣: Check Actions Tab

**What to do:**
1. Go to GitHub Actions tab
2. Look for "Exercise 3 - Advanced Python Workflow"
3. Click on the run
4. Watch as it processes the steps

**What you should see:**
Multiple steps running:
- ⏳ Checkout Code
- ⏳ Set up Python
- ⏳ Print Welcome Message
- ⏳ etc.

---

## STEP 5️⃣: View Python Version

**What to do:**
1. Click on step "Print Python Version"
2. View the output

**What you should see:**
```
Run python --version
Python 3.10.x (version number may vary)
```

---

## STEP 6️⃣: View Counting Script Output

**What to do:**
1. Click on step "Run Counting Script"
2. View the full output

**What you should see:**
```
Run python -c "
python -c "
print('Starting counter...')
for i in range(1, 6):
    print(f'Count: {i}')
print('Counter completed!')
"
Starting counter...
Count: 1
Count: 2
Count: 3
Count: 4
Count: 5
Counter completed!
```

---

## STEP 7️⃣: View Package Installation

**What to do:**
1. Click on step "Install Example Package"
2. View the output

**What you should see:**
```
Successfully installed requests-x.x.x
```

---

## STEP 8️⃣: View Requests Version

**What to do:**
1. Click on step "Verify Installation"
2. View the output

**What you should see:**
```
Requests library version: 2.x.x
```

---

## STEP 9️⃣: Create Final Pull Request

**What to do:**
1. Go to Pull Requests tab
2. Click "New pull request"
3. Set Base: `main`, Compare: `dev`
4. Click "Create pull request"
5. Add title: "Final Exercise 3 Merge"
6. Click "Create pull request"

**What you should see:**
- PR created
- Workflow runs automatically on PR
- Status checks appear

---

## STEP 🔟: Merge Final PR

**What to do:**
1. Wait for checks to pass (green checkmark)
2. Click "Merge pull request"
3. Click "Confirm merge"

**What you should see:**
```
Pull request successfully merged and closed
```

🎉 **EXERCISE 3 COMPLETE!**

---

## ✅ FINAL CHECKLIST

Before submitting your project, verify:

- [ ] Repository `github-actions-lab` exists on GitHub
- [ ] `.github/workflows/` folder visible in Code tab
- [ ] `hello.yml` file visible in workflows folder
- [ ] `dev-branch.yml` file visible in workflows folder
- [ ] `advanced.yml` file visible in workflows folder
- [ ] At least 3 workflow runs show in Actions tab
- [ ] Exercise 1 shows "Hello from GitHub Actions!"
- [ ] Exercise 2 triggered on dev push
- [ ] Exercise 3 shows Python 3.10 version
- [ ] Exercise 3 shows counting (1-5) output
- [ ] Exercise 3 shows "Requests library version"
- [ ] All pull requests merged successfully
- [ ] Network graph shows branch merges

---

## 🚨 TROUBLESHOOTING

### Problem: "Permission denied" when running git
**Solution**: Open PowerShell as Administrator
- Right-click PowerShell
- Click "Run as administrator"
- Re-run git commands

### Problem: Workflow doesn't run
**Solution**: 
1. Check `.github/workflows/` folder exists
2. Check file ends with `.yml`
3. Refresh Actions tab (F5)
4. Wait 30 seconds for GitHub to process

### Problem: "fatal: destination path already exists"
**Solution**: You already initialized. Use:
```bash
git status
```
instead of `git init` again

### Problem: "The workflow is not valid"
**Solution**: 
1. Check YAML indentation (use spaces, not tabs)
2. Validate at https://yamllint.com/
3. Fix errors and try again

### Problem: Merge conflicts
**Solution**:
1. Contact your instructor
2. Or recreate the repository fresh

---

## 📚 LEARNING RESOURCES

- **GitHub Actions Docs**: https://docs.github.com/actions
- **YAML Tutorial**: https://www.json2yaml.com/
- **Git Commands**: https://git-scm.com/book/en/v2
- **Python in GitHub Actions**: https://github.com/actions/setup-python

---

## 🎓 WHAT YOU'VE LEARNED

1. ✅ How to create GitHub workflows
2. ✅ How to trigger workflows on events
3. ✅ How to use GitHub Actions
4. ✅ How to work with branches
5. ✅ How to create pull requests
6. ✅ How to set up Python environments
7. ✅ How to run scripts in workflows
8. ✅ How to install packages
9. ✅ Basic Git commands
10. ✅ GitHub user interface

You're now ready for real-world GitHub Actions projects! 🚀

