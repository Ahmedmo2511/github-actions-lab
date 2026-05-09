# Lab 10: Git Commands - Copy & Paste Ready

## 📋 All Commands You Need

### ✅ STEP 1: Navigate to Project
```bash
cd c:\Users\DELL\OneDrive\Desktop\Agile\github-actions-lab
```

### ✅ STEP 2: Check Current Status
```bash
git status
```

**You should see:**
```
On branch main
Changes not staged for commit:
  new file:   scripts/math_utils.py
  new file:   scripts/test_math_utils.py
  new file:   .github/workflows/pytest-exercise1.yml
  new file:   .github/workflows/pytest-exercise2.yml
  new file:   .github/workflows/pytest-exercise3.yml
  new file:   LAB10_GUIDE.md
  new file:   LAB10_SCREENSHOTS.md
```

### ✅ STEP 3: Add All New Files
```bash
git add .
```

### ✅ STEP 4: Verify Files are Staged
```bash
git status
```

**You should see:**
```
On branch main
Changes to be committed:
  new file:   scripts/math_utils.py
  new file:   scripts/test_math_utils.py
  [all files showing as "new file"]
```

### ✅ STEP 5: Create Commit
```bash
git commit -m "Lab 10: Add pytest workflows with matrix strategy and artifacts"
```

**You should see:**
```
[main abc1234] Lab 10: Add pytest workflows with matrix strategy and artifacts
 5 files changed, 850 insertions(+)
 create mode 100644 scripts/math_utils.py
 create mode 100644 scripts/test_math_utils.py
 create mode 100644 .github/workflows/pytest-exercise1.yml
 create mode 100644 .github/workflows/pytest-exercise2.yml
 create mode 100644 .github/workflows/pytest-exercise3.yml
```

### ✅ STEP 6: Push to GitHub
```bash
git push origin main
```

**You should see:**
```
Enumerating objects: 10, done.
Counting objects: 100% (10/10), done.
Delta compression using up to 8 threads
Compressing objects: 100% (8/8), done.
Writing objects: 100% (8/8), 1.52 KiB | 758.00 KiB/s, done.
Total 8 (delta 2), reused 0 (delta 0), pack-reused 0
To https://github.com/YOUR_USERNAME/github-actions-lab.git
   def4567..abc1234  main -> main
```

---

## 🎯 COMPLETE SEQUENCE (Copy & Paste All)

If you want to run all commands at once, copy this entire block:

```bash
cd c:\Users\DELL\OneDrive\Desktop\Agile\github-actions-lab
git add .
git commit -m "Lab 10: Add pytest workflows with matrix strategy and artifacts"
git push origin main
```

---

## ✅ VERIFICATION COMMANDS

### Check Your Branch
```bash
git branch
```

Should show:
```
* main
```

### View Commit History
```bash
git log --oneline
```

Should show recent commit:
```
abc1234 Lab 10: Add pytest workflows with matrix strategy and artifacts
def5678 Initial commit: Complete GitHub Actions Lab project...
```

### Check Remote URL
```bash
git remote -v
```

Should show:
```
origin  https://github.com/YOUR_USERNAME/github-actions-lab.git (fetch)
origin  https://github.com/YOUR_USERNAME/github-actions-lab.git (push)
```

### List All Files Tracked by Git
```bash
git ls-files
```

Should include:
```
.github/workflows/pytest-exercise1.yml
.github/workflows/pytest-exercise2.yml
.github/workflows/pytest-exercise3.yml
scripts/math_utils.py
scripts/test_math_utils.py
LAB10_GUIDE.md
LAB10_SCREENSHOTS.md
```

---

## 🔄 IF YOU MAKE MISTAKES

### Undo Last Commit (Keep Changes)
```bash
git reset HEAD~1
```

### Undo Last Commit (Delete Changes)
```bash
git reset --hard HEAD~1
```

### View Last Commit Details
```bash
git show
```

### Fix Commit Message
```bash
git commit --amend -m "New message here"
```

### Check What Changed
```bash
git diff
```

---

## 📝 ADDITIONAL USEFUL COMMANDS

### Check File Status
```bash
git status scripts/math_utils.py
```

### Add Specific File Only
```bash
git add scripts/math_utils.py
```

### Remove File from Staging
```bash
git reset scripts/math_utils.py
```

### View Staged Changes
```bash
git diff --staged
```

### View Commits by Author
```bash
git log --author="GitHub User"
```

### See Graph of Commits
```bash
git log --graph --oneline --all
```

---

## 🆘 TROUBLESHOOTING

### Permission Denied Error
**Problem:** `fatal: could not read Username...`

**Solution:** 
1. Run PowerShell as Administrator
2. Or update GitHub credentials in Credential Manager

### File Already Tracked Error
**Problem:** `error: The following untracked working tree files would be overwritten by merge`

**Solution:**
```bash
git clean -fd
git reset --hard HEAD
```

### Can't Push Changes
**Problem:** `fatal: The current branch has no upstream branch`

**Solution:**
```bash
git push -u origin main
```

---

## 💡 COMMAND EXPLANATIONS

| Command | What It Does |
|---------|-------------|
| `git status` | Shows changed files |
| `git add .` | Stages all changes |
| `git commit -m "msg"` | Creates commit with message |
| `git push origin main` | Uploads to GitHub on main branch |
| `git log` | Shows commit history |
| `git diff` | Shows detailed changes |
| `git reset` | Undoes staging |
| `git branch` | Shows current branch |

---

## 🎯 WORKFLOW

**Standard workflow for Lab 10:**

1. Create files (already done) ✅
2. Check status: `git status`
3. Add files: `git add .`
4. Create commit: `git commit -m "message"`
5. Push to GitHub: `git push origin main`
6. Verify on GitHub ✅

**Always verify on GitHub after pushing!**

---

## 📋 CHECKLIST FOR SUCCESSFUL PUSH

- [ ] All new files created (scripts/, workflows)
- [ ] Ran `git add .`
- [ ] Ran `git commit -m "..."`
- [ ] Ran `git push origin main`
- [ ] Went to GitHub and refreshed
- [ ] See new files in Code tab
- [ ] Workflows start running automatically
- [ ] Actions tab shows workflows running

---

## 🚀 NEXT STEPS AFTER PUSH

Once everything is on GitHub:

1. **Go to Actions tab** in your repository
2. **Watch workflows run** (might take 30-60 seconds)
3. **Verify all three workflows appear**
4. **Click on each workflow to view results**
5. **Take screenshots** for your PDF report
6. **Download test report artifacts** from Exercise 3

---

## 📞 IF WORKFLOWS DON'T RUN

**Check:**
- [ ] Files are in `.github/workflows/` (not `.github\workflows\`)
- [ ] File extensions are `.yml` (not `.yaml`)
- [ ] YAML indentation is correct (use spaces, not tabs)
- [ ] Repository is public (for free GitHub Actions)
- [ ] Refresh Actions tab (F5)
- [ ] Wait 30 seconds for GitHub to process

**Validate YAML:**
Go to https://yamllint.com/ and paste your workflow file.

