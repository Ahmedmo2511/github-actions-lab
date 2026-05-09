# GitHub Actions Lab - Quick Start Summary

## 📂 Project Structure

```
github-actions-lab/
├── .github/
│   └── workflows/
│       ├── hello.yml           (Exercise 1)
│       ├── dev-branch.yml      (Exercise 2)
│       └── advanced.yml        (Exercise 3)
├── README.md                   (Complete guide with all git commands)
├── BEGINNER_GUIDE.md          (Step-by-step walkthrough)
├── GITHUB_UI_GUIDE.md         (Where to find things + screenshots list)
├── YAML_REFERENCE.md          (YAML syntax and ready-to-copy files)
└── QUICK_START.md             (This file)
```

---

## 🎯 Three Exercises at a Glance

| Exercise | File | Trigger | Output |
|----------|------|---------|--------|
| 1 | `hello.yml` | Every push | "Hello from GitHub Actions!" |
| 2 | `dev-branch.yml` | Dev push + PR to main | Branch and event info |
| 3 | `advanced.yml` | Dev/main push + PR | Python 3.10, counting script, packages |

---

## ⚡ Quick Commands Cheat Sheet

### First Time Setup
```bash
cd github-actions-lab
git init
git config user.name "Your Name"
git config user.email "your@email.com"
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/USERNAME/github-actions-lab.git
git branch -M main
git push -u origin main
```

### Working with Branches
```bash
git checkout -b dev          # Create dev branch
git push -u origin dev       # Push to GitHub
git add .
git commit -m "Message"
git push origin dev          # Push changes
```

### Merge to Main
```bash
git checkout main
git pull origin main         # Get latest main
# Create PR on GitHub, then:
git pull origin main         # Sync after merge
```

---

## 📋 File Descriptions

### README.md
- Complete step-by-step instructions for all exercises
- All git commands with explanations
- Workflow files reference
- Troubleshooting guide
- **Start here for full details**

### BEGINNER_GUIDE.md
- Number all steps (Step 1️⃣, Step 2️⃣, etc.)
- "What to do" and "What you should see"
- PowerShell examples
- Perfect for beginners
- **Start here if you're new to Git/GitHub**

### GITHUB_UI_GUIDE.md
- Where to find Actions tab
- How to view workflow logs
- PR status checks location
- **Complete screenshot checklist for PDF**
- Network graph visualization
- **Use this to create your deliverables**

### YAML_REFERENCE.md
- All three workflow files ready to copy
- YAML syntax rules and examples
- Common GitHub Actions
- Environment variables
- YAML validation tips
- **Copy-paste all workflow YAML from here**

---

## 📸 Required Screenshots for PDF (Quick Checklist)

**Exercise 1** (4 screenshots):
- [ ] Repository showing .github/workflows folder
- [ ] hello.yml file content
- [ ] Workflow run with green checkmark
- [ ] Logs showing "Hello from GitHub Actions!"

**Exercise 2** (7 screenshots):
- [ ] Dev branch created (Branches tab)
- [ ] dev-branch.yml file content
- [ ] Pull request created
- [ ] Status checks on PR
- [ ] Status check details
- [ ] Workflow triggered by push
- [ ] PR merged

**Exercise 3** (7 screenshots):
- [ ] advanced.yml file content
- [ ] Workflow running (with steps)
- [ ] Python version output
- [ ] Counting script output (1-5)
- [ ] Package installation
- [ ] Requests library version
- [ ] Complete workflow success

**Additional** (4 screenshots):
- [ ] Network graph (Insights → Network)
- [ ] Complete file structure
- [ ] All three workflows listed
- [ ] Commit history

**Total: 22 screenshots minimum**

---

## 🔄 Exercise Progression

### Exercise 1: Basics
1. Create local repo
2. Push to GitHub
3. Workflow triggers automatically
4. View simple output

### Exercise 2: Branching
1. Create dev branch
2. Push to dev triggers workflow
3. Create PR triggers workflow
4. See status checks on PR
5. Merge to main

### Exercise 3: Advanced
1. Work on dev branch
2. Set up Python environment
3. Run Python scripts
4. Install packages
5. View all outputs in logs

---

## 🌐 Important URLs

- **Your repository**: https://github.com/YOUR_USERNAME/github-actions-lab
- **Actions tab**: https://github.com/YOUR_USERNAME/github-actions-lab/actions
- **Pull Requests**: https://github.com/YOUR_USERNAME/github-actions-lab/pulls
- **Network Graph**: https://github.com/YOUR_USERNAME/github-actions-lab/network
- **Settings**: https://github.com/YOUR_USERNAME/github-actions-lab/settings

---

## 🎓 Key Concepts

- **Workflow**: Automated process triggered by GitHub events
- **Job**: Collection of steps that run together
- **Step**: Individual command or action
- **Trigger**: Event that starts the workflow (push, PR, etc.)
- **Runner**: Virtual machine executing the workflow
- **Branch**: Parallel version of code
- **Pull Request**: Request to merge changes into main
- **Status Check**: Workflow result displayed on PR

---

## ✅ Submission Checklist

Before submitting your lab:

- [ ] Repository created on GitHub
- [ ] All three workflow files created
- [ ] All three exercises completed
- [ ] At least one successful run for each workflow
- [ ] Pull requests created and merged
- [ ] Branch created and used
- [ ] All documentation completed
- [ ] 22+ screenshots captured
- [ ] PDF report created with screenshots
- [ ] All git commands documented

---

## 🚀 Next Learning Steps

After completing this lab:

1. **Matrix Builds**: Run tests on multiple Python versions
2. **Artifacts**: Save and download build outputs
3. **Secrets**: Use API keys and passwords securely
4. **Caching**: Speed up workflows with dependency caching
5. **Deployment**: Automatically deploy code on successful build
6. **Notifications**: Send alerts on workflow success/failure
7. **Scheduled Runs**: Run workflows on a schedule (cron)
8. **Custom Actions**: Write your own GitHub Actions
9. **Third-party Services**: Integrate with Slack, Discord, etc.
10. **Advanced Testing**: Add unit tests and coverage reports

---

## 📚 Official Documentation

- GitHub Actions: https://docs.github.com/actions
- Workflows: https://docs.github.com/actions/workflows
- Setup-Python Action: https://github.com/actions/setup-python
- Git Documentation: https://git-scm.com/docs

---

## 🆘 Common Issues & Fixes

| Issue | Solution |
|-------|----------|
| Workflow doesn't run | Check `.github/workflows/` path and `.yml` extension |
| YAML syntax error | Use https://yamllint.com/ to validate |
| Can't push to GitHub | Verify git remote: `git remote -v` |
| Merge conflicts | Pull latest main: `git pull origin main` |
| Python version not found | Check Python 3.10 is valid on ubuntu-latest |
| Package installation fails | Check pip package name is correct |
| Permission denied errors | Run PowerShell as Administrator |

---

## 📖 Quick Reference: YAML Structure

```yaml
name: Workflow Name                 # Display name in Actions tab
on: [push, pull_request]            # Events that trigger workflow
jobs:                               # Start of jobs section
  job-name:                         # Job identifier
    runs-on: ubuntu-latest          # Virtual machine type
    steps:                          # Steps in this job
      - name: Step description      # Human-readable name
        run: command                # Shell command to run
      - uses: action/path@version   # Use a GitHub Action
        with:                       # Parameters for action
          param-name: value
```

---

## 🎯 Success Indicators

You know you've completed the lab when:

✅ Exercise 1
- Workflow runs on every push
- Output shows "Hello from GitHub Actions!"

✅ Exercise 2
- Workflow only triggers on dev branch pushes
- Workflow triggers on PRs to main
- Status checks appear on PR page

✅ Exercise 3
- Workflow sets up Python 3.10
- Counting script runs (outputs 1-5)
- Pip installs requests package
- Package version displays in logs

✅ All Exercises
- All three workflows exist in `.github/workflows/`
- Branches created and used (main, dev)
- Pull requests created and merged
- 22+ screenshots captured
- PDF report submitted with all screenshots

---

## 📝 Git Commands Quick Ref

```bash
git init                    # Initialize repository
git add .                   # Stage all files
git commit -m "message"     # Create commit
git push origin branch      # Push to GitHub
git pull origin branch      # Get latest from GitHub
git checkout -b branch      # Create and switch to branch
git branch                  # List branches
git status                  # Check current status
git log --oneline          # View commit history
```

---

## 🎉 You're Ready!

You now have everything you need:
- ✅ Project structure created
- ✅ All three workflows configured
- ✅ Complete documentation
- ✅ Step-by-step guides
- ✅ Screenshot checklist
- ✅ Git commands reference
- ✅ Beginner-friendly explanations

**Next step**: Follow BEGINNER_GUIDE.md step-by-step and start with Exercise 1!

---

## 📞 Getting Help

If something goes wrong:
1. Check BEGINNER_GUIDE.md for your specific step
2. Review GITHUB_UI_GUIDE.md for UI-related issues
3. Check the troubleshooting section in README.md
4. Validate YAML at https://yamllint.com/
5. Check workflow logs in GitHub Actions tab

Good luck with your GitHub Actions lab! 🚀

