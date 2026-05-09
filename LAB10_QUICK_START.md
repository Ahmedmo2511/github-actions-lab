# Lab 10: Quick Reference

## 📚 Lab 10: More on GitHub Actions

**Focus**: Testing, Matrix Builds, Artifacts

---

## 🎯 Three Exercises Summary

| Exercise | File | Topic | Key Feature |
|----------|------|-------|------------|
| 1 | `pytest-exercise1.yml` | Basic Testing | Single OS (ubuntu-latest) |
| 2 | `pytest-exercise2.yml` | Matrix Strategy | 3 OS simultaneously (ubuntu, windows, macos) |
| 3 | `pytest-exercise3.yml` | Artifacts | Generate and upload test reports |

---

## 📁 FILES CREATED

### Python Test Files
```
scripts/
├── math_utils.py          (Functions: add, subtract)
└── test_math_utils.py     (Tests: test_add, test_subtract)
```

### Workflow Files
```
.github/workflows/
├── pytest-exercise1.yml   (Basic: ubuntu only)
├── pytest-exercise2.yml   (Matrix: 3 OS parallel)
└── pytest-exercise3.yml   (Artifacts: reports + downloads)
```

### Documentation
```
LAB10_GUIDE.md            (Complete guide)
LAB10_SCREENSHOTS.md      (18 screenshots needed)
LAB10_GIT_COMMANDS.md     (All git commands)
LAB10_QUICK_START.md      (This file)
```

---

## 🚀 5-MINUTE SETUP

### 1. Verify Files Exist
```bash
ls scripts/
ls .github/workflows/pytest*.yml
```

### 2. Stage & Commit
```bash
git add .
git commit -m "Lab 10: Add pytest workflows with matrix and artifacts"
```

### 3. Push to GitHub
```bash
git push origin main
```

### 4. Watch Workflows
- Go to GitHub Actions tab
- Watch three workflows run
- Each tests on 3 different OS

### 5. Download Artifacts
- Go to Exercise 3 workflow run
- Scroll to Artifacts section
- Download test reports

---

## 💡 KEY CONCEPTS

### Pytest
```python
def test_add():
    assert add(2, 3) == 5    # Test passes if true
```

### Matrix Strategy
```yaml
strategy:
  matrix:
    os: [ubuntu-latest, windows-latest, macos-latest]
runs-on: ${{ matrix.os }}
```
**Result**: Same job runs 3 times on different OS

### JUnit XML Report
```bash
pytest -v scripts/ --junitxml=pytest-report.xml
```
Creates downloadable test report

### Upload Artifact
```yaml
- uses: actions/upload-artifact@v4
  with:
    name: pytest-report_${{ matrix.os }}
    path: pytest-report.xml
```
Saves file for download after workflow

---

## 📊 EXERCISE 1: BASIC PYTEST

**Trigger**: Push or PR  
**Runs On**: ubuntu-latest (Linux)  
**Steps**:
1. Checkout code
2. Setup Python 3.10
3. Install pytest
4. Run: `pytest -v scripts/`

**Expected Output**:
```
scripts/test_math_utils.py::test_add PASSED
scripts/test_math_utils.py::test_subtract PASSED
====== 2 passed in 0.05s ======
```

---

## 📊 EXERCISE 2: MATRIX STRATEGY

**Trigger**: Push or PR  
**Runs On**: 3 OS simultaneously
- ubuntu-latest (Linux)
- windows-latest (Windows)
- macos-latest (macOS)

**How It Works**:
- Creates 3 parallel jobs
- Each runs same tests
- Each on different OS
- **Much faster than sequential!**

**Expected**: Three ✅ checkmarks in Actions tab

---

## 📊 EXERCISE 3: ARTIFACTS

**Trigger**: Push or PR  
**Runs On**: 3 OS (like Exercise 2)  

**New Steps**:
1. Generate XML report: `--junitxml=pytest-report.xml`
2. Upload artifact to GitHub

**Expected**: Download 3 test reports from Artifacts section

---

## 🔍 WHERE TO FIND THINGS

| What | Where |
|------|-------|
| Workflows | GitHub → Actions tab |
| Matrix Jobs | Click workflow run → See 3 jobs |
| Test Output | Click "Run pytest" step in job |
| Artifacts | Scroll bottom of workflow run |
| XML Report | Download artifact → Extract ZIP |
| Code | GitHub → Code tab → `scripts/` folder |

---

## 📸 SCREENSHOTS NEEDED

**Exercise 1** (4 screenshots):
- Code structure
- Workflow file
- Workflow run
- Pytest output

**Exercise 2** (5 screenshots):
- Matrix workflow file
- Three matrix jobs
- Ubuntu logs
- Windows logs
- macOS logs

**Exercise 3** (6 screenshots):
- Exercise 3 workflow file
- All jobs complete
- Artifacts available
- Download artifacts
- XML report content
- Speed comparison

**Additional** (3 screenshots):
- All workflows list
- Complete code structure
- Commit history

**Total: 18 screenshots**

---

## ⚡ GIT COMMANDS

### Push Lab 10 to GitHub
```bash
cd c:\Users\DELL\OneDrive\Desktop\Agile\github-actions-lab
git add .
git commit -m "Lab 10: Add pytest workflows with matrix strategy and artifacts"
git push origin main
```

### Verify
```bash
git status          # Should show clean
git log --oneline   # Should show new commit
```

---

## ✅ CHECKLIST

- [ ] `scripts/math_utils.py` created
- [ ] `scripts/test_math_utils.py` created
- [ ] `pytest-exercise1.yml` created
- [ ] `pytest-exercise2.yml` created
- [ ] `pytest-exercise3.yml` created
- [ ] Git add, commit, push completed
- [ ] Workflows running on GitHub
- [ ] All 18 screenshots captured
- [ ] PDF report created

---

## 🎓 WHAT YOU LEARNED

✅ Write Python test functions  
✅ Use pytest for automated testing  
✅ Matrix builds (multiple OS)  
✅ Parallel job execution  
✅ JUnit XML reports  
✅ Workflow artifacts  
✅ Professional CI/CD practices  

---

## 🔗 DOCUMENTATION FILES

| File | Purpose |
|------|---------|
| LAB10_GUIDE.md | Complete step-by-step guide |
| LAB10_SCREENSHOTS.md | Where to find + screenshot list |
| LAB10_GIT_COMMANDS.md | All git commands explained |
| LAB10_QUICK_START.md | This quick reference |

---

## 🚀 NEXT STEPS

1. **Execute**: Follow LAB10_GUIDE.md
2. **Test**: Verify workflows on GitHub
3. **Capture**: Take 18 screenshots (see LAB10_SCREENSHOTS.md)
4. **Report**: Create PDF with screenshots
5. **Submit**: Submit completed lab

---

**Ready to start?** Open LAB10_GUIDE.md for complete instructions! 🎯

