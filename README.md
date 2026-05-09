# GitHub Actions Lab - Complete Guide

## Project Overview
This project teaches GitHub Actions with three progressive exercises:
- **Exercise 1**: Basic workflow that prints a hello message
- **Exercise 2**: Conditional triggers (dev branch & pull requests)
- **Exercise 3**: Advanced workflow with Python setup and package management

---

## PART 1: INITIAL SETUP (Exercise 1)

### Step 1: Initialize Git Repository
```bash
cd github-actions-lab
git init
git config user.name "Your Name"
git config user.email "your.email@example.com"
```

### Step 2: Create Workflow Files
The `.github/workflows/` directory and `hello.yml` file are already created.

### Step 3: Add All Files to Git
```bash
git add .
```

### Step 4: Commit the Changes
```bash
git commit -m "Initial commit: Add Exercise 1 workflow"
```

### Step 5: Create Repository on GitHub
1. Go to https://github.com/new
2. Repository name: `github-actions-lab`
3. Leave it PUBLIC (for free GitHub Actions)
4. Click "Create repository"

### Step 6: Add Remote and Push
```bash
git remote add origin https://github.com/YOUR_USERNAME/github-actions-lab.git
git branch -M main
git push -u origin main
```

**Expected Result**: Your first workflow runs automatically on push!

---

## PART 2: BRANCH WORKFLOW (Exercise 2)

### Step 7: Create and Switch to Dev Branch
```bash
git checkout -b dev
```
*Or use the newer syntax:*
```bash
git switch -c dev
```

### Step 8: Verify Your Branch
```bash
git branch
```
*Output will show:*
```
  main
* dev
```

### Step 9: Update Workflow (Optional - Add dev-branch.yml)
The `dev-branch.yml` file handles both dev pushes and PR to main.

### Step 10: Commit Changes to Dev
```bash
git add .
git commit -m "Update: Add Exercise 2 workflow"
```

### Step 11: Push Dev Branch to GitHub
```bash
git push -u origin dev
```

### Step 12: Create a Pull Request
On GitHub:
1. Go to your repository
2. Click "Pull requests" tab
3. Click "New pull request"
4. Base: `main` ← Compare: `dev`
5. Click "Create pull request"
6. Add title: "Add Exercise 2 workflow"
7. Click "Create pull request"

**Expected Results**:
- Workflow runs on each dev push
- Workflow runs when PR is created/updated
- Status check appears on the PR

### Step 13: Merge the Pull Request
On GitHub:
1. Click "Merge pull request"
2. Click "Confirm merge"
3. Click "Delete branch" (optional)

### Step 14: Sync Local Repo
```bash
git checkout main
git pull origin main
```

---

## PART 3: ADVANCED WORKFLOW (Exercise 3)

### Step 15: Update Dev Branch with Advanced Workflow
```bash
git checkout dev
```

### Step 16: Add Advanced Workflow File
The `advanced.yml` file is already created with Python setup.

### Step 17: Commit and Push
```bash
git add .
git commit -m "Add Exercise 3: Advanced Python workflow"
git push origin dev
```

### Step 18: Test on Dev Branch
Push another commit to trigger the workflow:
```bash
echo "# Testing Advanced Workflow" >> README.md
git add README.md
git commit -m "Test advanced workflow"
git push origin dev
```

### Step 19: Create Another PR to Main
On GitHub:
1. Create a new pull request: `dev` → `main`
2. Watch the advanced workflow run
3. See Python version and counting messages in logs

### Step 20: Merge to Main
```bash
# On GitHub: Merge the PR
# Then sync locally:
git checkout main
git pull origin main
```

---

## USEFUL GIT COMMANDS REFERENCE

### Viewing Status & History
```bash
git status                    # See what's changed
git log --oneline            # See commit history
git log --graph --all        # See branch graph
```

### Branch Management
```bash
git branch                   # List branches
git branch -a               # List all branches (local & remote)
git branch -d dev           # Delete local branch
git push origin --delete dev # Delete remote branch
```

### Undoing Changes
```bash
git restore <filename>       # Undo changes in working directory
git reset HEAD~1            # Undo last commit (keep changes)
git revert <commit-hash>    # Create new commit that undoes changes
```

### Checking Out & Switching
```bash
git checkout main           # Switch to main branch
git checkout -b new-branch  # Create and switch to new branch
git switch main             # Modern alternative to checkout
```

### Pull vs Fetch
```bash
git fetch origin            # Download changes (no merge)
git pull origin main        # Download AND merge changes
```

---

## WORKFLOW FILES REFERENCE

### Exercise 1: hello.yml
Location: `.github/workflows/hello.yml`
Triggers: Every push
Jobs: 1 (prints hello message)

### Exercise 2: dev-branch.yml
Location: `.github/workflows/dev-branch.yml`
Triggers: 
- Push to `dev` branch
- Pull requests to `main` branch
Jobs: 1 (checks out code, prints info)

### Exercise 3: advanced.yml
Location: `.github/workflows/advanced.yml`
Triggers:
- Push to `dev` or `main`
- Pull requests to `main`
Jobs: 1 (Python 3.10, runs counting script, installs packages)

---

## YAML SYNTAX QUICK REFERENCE

```yaml
name: Workflow Name              # Display name
on: [push, pull_request]         # Trigger events
jobs:                            # Start of jobs
  job-name:                      # Unique job ID
    runs-on: ubuntu-latest       # Runner environment
    steps:                       # Steps in the job
      - name: Step Name          # Step description
        run: command             # Command to execute
        uses: action/path@v#     # GitHub Action to use
      - uses: actions/checkout@v4  # Check out code
      - uses: actions/setup-python@v5  # Set up Python
        with:                    # Action parameters
          python-version: '3.10'
```

---

## TROUBLESHOOTING GUIDE

### Workflow Doesn't Run
- ✅ Check that YAML is in `.github/workflows/` directory
- ✅ Verify the file ends with `.yml` or `.yaml`
- ✅ Check YAML syntax (use online validator: yamllint.com)
- ✅ Ensure trigger conditions are met

### Python Setup Issues
- ✅ Verify Python version exists (3.10 is stable)
- ✅ Ensure `pip install` has correct package names
- ✅ Check that scripts exit with code 0 (success)

### Push Not Triggering Workflow
- ✅ Workflow file must be on the branch being pushed
- ✅ File must be in `.github/workflows/` folder
- ✅ Wait 30 seconds for GitHub to process
- ✅ Refresh Actions tab (F5)

---

## FREQUENTLY USED COMMANDS

```bash
# Daily workflow
git add .
git commit -m "Description"
git push origin branch-name

# Create and test feature
git checkout -b feature-name
# Make changes...
git push -u origin feature-name
# Create PR on GitHub

# Update from main
git checkout dev
git pull origin main
git push origin dev
```

---

## Key Concepts

- **Repository**: Your project storage on GitHub
- **Branch**: Parallel version of code
- **Workflow**: Automated tasks triggered by events
- **Job**: A set of steps in a workflow
- **Step**: Individual command or action
- **Runner**: Virtual machine that executes the workflow
- **Artifact**: Files saved from workflow execution
- **Secret**: Secure variables (passwords, tokens)

---

## Next Steps

After completing this lab:
1. ✅ Modify workflows to run on different events
2. ✅ Add more steps to workflows
3. ✅ Use workflow artifacts
4. ✅ Add GitHub secrets for sensitive data
5. ✅ Create matrix builds (test multiple Python versions)
6. ✅ Add automatic deployment
7. ✅ Set up branch protection rules

