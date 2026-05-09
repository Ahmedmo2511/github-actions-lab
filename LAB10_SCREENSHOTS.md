# Lab 10: Where to Find Everything + Screenshots

## 🔍 FINDING THE ACTIONS TAB

### URL to Actions
```
https://github.com/YOUR_USERNAME/github-actions-lab/actions
```

### In GitHub UI
1. Go to your repository: `github-actions-lab`
2. Click **"Actions"** tab (top navigation)
3. You'll see all workflows listed on the left

---

## 📋 WORKFLOW LIST YOU'LL SEE

On the left sidebar:
- ✅ Exercise 1 - Hello GitHub Actions (old)
- ✅ Exercise 2 - Dev Branch & Pull Requests (old)
- ✅ Exercise 3 - Advanced Python Workflow (old)
- ✅ Run Automated Tests - Exercise 1 (NEW)
- ✅ Run Automated Tests - Exercise 2 (Matrix) (NEW)
- ✅ Run Automated Tests - Exercise 3 (Artifacts) (NEW)

---

## 🎯 MATRIX JOBS - WHERE TO FIND

### Location
1. Go to Actions tab
2. Click on "Run Automated Tests - Exercise 2 (Matrix)"
3. Click on a specific run

### What You'll See
**Three separate jobs displayed:**
- test (ubuntu-latest) 
- test (windows-latest)
- test (macos-latest)

Each shows:
- ✅ Green checkmark (passed)
- ⏱️ Execution time
- 📊 Job status

### Visual Layout
```
Summary
├─ test (ubuntu-latest) ✅ 45s
├─ test (windows-latest) ✅ 52s
└─ test (macos-latest) ✅ 49s

All jobs run at the same time!
```

### How to Expand a Job
1. Click on job name: "test (ubuntu-latest)"
2. See all steps expand:
   - Checkout Repository
   - Set up Python
   - Install dependencies
   - Run pytest

---

## 📦 ARTIFACTS - WHERE TO FIND & DOWNLOAD

### Location
1. Go to Actions tab
2. Click "Run Automated Tests - Exercise 3 (Artifacts)"
3. Click on a specific run
4. Look for **"Artifacts"** section at the bottom

### What You'll See
Three downloadable artifacts:
- `pytest-report_ubuntu-latest` 📥
- `pytest-report_windows-latest` 📥
- `pytest-report_macos-latest` 📥

### How to Download
1. Click on artifact name
2. ZIP file downloads automatically
3. Extract the ZIP
4. Inside is `pytest-report.xml`

### Viewing the XML Report
**Option 1: Text Editor**
- Right-click file
- Open with Notepad
- See raw XML content

**Option 2: Web Browser**
- Drag and drop into browser
- Some browsers show formatted view
- Click refresh if needed

**Option 3: XML Viewer**
- Online: https://www.beautifier.io/
- Paste content, get formatted view

---

## 📝 PYTEST REPORT.XML CONTENT

**Example Content:**
```xml
<?xml version="1.0" encoding="utf-8"?>
<testsuite name="pytest" errors="0" failures="0" skipped="0" tests="2" time="0.123">
  <testcase classname="test_math_utils" name="test_add" time="0.001"/>
  <testcase classname="test_math_utils" name="test_subtract" time="0.001"/>
</testsuite>
```

**What Each Part Means:**
- `errors="0"` - No errors
- `failures="0"` - No failures
- `skipped="0"` - No skipped tests
- `tests="2"` - 2 total tests run
- `time="0.123"` - Total execution time

---

## 📊 WORKFLOW RUN DETAILS

### Exercise 1 Output (Single OS)
```
Run Automated Tests - Exercise 1
├─ test
   ├─ Checkout Repository ✅
   ├─ Set up Python ✅
   ├─ Install dependencies ✅
   └─ Run pytest ✅
       Output:
       scripts/test_math_utils.py::test_add PASSED
       scripts/test_math_utils.py::test_subtract PASSED
       ====== 2 passed in 0.05s ======
```

### Exercise 2 Output (Matrix - 3 OS)
```
Run Automated Tests - Exercise 2 (Matrix)
├─ test (ubuntu-latest) ✅
│  ├─ Checkout Repository ✅
│  ├─ Set up Python ✅
│  ├─ Install dependencies ✅
│  └─ Run pytest ✅
│
├─ test (windows-latest) ✅
│  ├─ Checkout Repository ✅
│  ├─ Set up Python ✅
│  ├─ Install dependencies ✅
│  └─ Run pytest ✅
│
└─ test (macos-latest) ✅
   ├─ Checkout Repository ✅
   ├─ Set up Python ✅
   ├─ Install dependencies ✅
   └─ Run pytest ✅
```

### Exercise 3 Output (Matrix + Artifacts)
```
Run Automated Tests - Exercise 3 (Artifacts)
├─ test (ubuntu-latest) ✅
│  └─ Run pytest (generate junit xml) ✅
│  └─ Upload test report artifact ✅
│
├─ test (windows-latest) ✅
│  └─ Run pytest (generate junit xml) ✅
│  └─ Upload test report artifact ✅
│
└─ test (macos-latest) ✅
   └─ Run pytest (generate junit xml) ✅
   └─ Upload test report artifact ✅

ARTIFACTS:
📥 pytest-report_ubuntu-latest
📥 pytest-report_windows-latest
📥 pytest-report_macos-latest
```

---

## 📸 SCREENSHOTS REQUIRED FOR PDF DELIVERABLE

### Exercise 1 Screenshots (4 total)

**Screenshot 1.1: Code Tab - New Structure**
- Location: Code tab in GitHub
- Show: `scripts/` folder visible
- Show: `math_utils.py` and `test_math_utils.py` files
- Capture: Folder structure expanded

**Screenshot 1.2: Workflow File**
- Location: Code → `.github/workflows/` → `pytest-exercise1.yml`
- Show: Full workflow YAML code
- Capture: Entire file content visible

**Screenshot 1.3: Workflow Run**
- Location: Actions → "Run Automated Tests - Exercise 1" → [Latest Run]
- Show: Green checkmark
- Show: Job name "test"
- Show: Status "Completed successfully"

**Screenshot 1.4: Pytest Output**
- Location: Same run → Click "Run pytest" step
- Show: Test output:
  ```
  scripts/test_math_utils.py::test_add PASSED
  scripts/test_math_utils.py::test_subtract PASSED
  ====== 2 passed in 0.05s ======
  ```
- Capture: Both test results visible

---

### Exercise 2 Screenshots (5 total)

**Screenshot 2.1: Matrix Workflow File**
- Location: Code → `.github/workflows/` → `pytest-exercise2.yml`
- Show: Strategy section:
  ```yaml
  strategy:
    matrix:
      os: [ubuntu-latest, windows-latest, macos-latest]
  ```
- Show: `runs-on: ${{ matrix.os }}`

**Screenshot 2.2: Three Matrix Jobs**
- Location: Actions → "Run Automated Tests - Exercise 2 (Matrix)" → [Latest Run]
- Show: Summary with three jobs:
  - test (ubuntu-latest) ✅
  - test (windows-latest) ✅
  - test (macos-latest) ✅

**Screenshot 2.3: Ubuntu Job Logs**
- Location: Same run → Click "test (ubuntu-latest)"
- Show: Steps expanded
- Show: All steps passed (Checkout, Setup Python, Install, Run pytest)

**Screenshot 2.4: Windows Job Logs**
- Location: Same run → Click "test (windows-latest)"
- Show: Steps expanded
- Show: All steps passed

**Screenshot 2.5: macOS Job Logs**
- Location: Same run → Click "test (macos-latest)"
- Show: Steps expanded
- Show: All steps passed

---

### Exercise 3 Screenshots (6 total)

**Screenshot 3.1: Exercise 3 Workflow File**
- Location: Code → `.github/workflows/` → `pytest-exercise3.yml`
- Show: New steps visible:
  ```yaml
  - name: Run pytest (generate junit xml)
    run: pytest -v scripts/ --junitxml=pytest-report.xml
  
  - name: Upload test report artifact
    uses: actions/upload-artifact@v4
  ```

**Screenshot 3.2: All Three Jobs Complete**
- Location: Actions → "Run Automated Tests - Exercise 3 (Artifacts)" → [Latest Run]
- Show: Summary with three jobs all ✅

**Screenshot 3.3: Artifacts Available**
- Location: Same run → Scroll to bottom
- Show: **Artifacts** section with three files:
  - pytest-report_ubuntu-latest
  - pytest-report_windows-latest
  - pytest-report_macos-latest

**Screenshot 3.4: Download Artifacts**
- Show: Click on "pytest-report_ubuntu-latest"
- Show: ZIP download initiated
- Capture: File name visible

**Screenshot 3.5: Report Content**
- Location: Extract downloaded ZIP → Open `pytest-report.xml`
- Show: XML file opened in text editor or browser
- Show: Test results in XML format
- Show: `tests="2"` attribute
- Show: `PASSED` testcases

**Screenshot 3.6: Matrix Speed Comparison**
- Location: Summary of Exercise 3 run
- Show: Total execution time (approximately 2-3 minutes for all 3 OS)
- Annotation: "Three OS running in parallel = much faster than sequential"

---

### Additional Screenshots (3 total)

**Screenshot A1: All Six Workflows**
- Location: Actions tab left sidebar
- Show: All workflow names listed:
  - Exercise 1 - Hello GitHub Actions
  - Exercise 2 - Dev Branch & Pull Requests
  - Exercise 3 - Advanced Python Workflow
  - Run Automated Tests - Exercise 1
  - Run Automated Tests - Exercise 2 (Matrix)
  - Run Automated Tests - Exercise 3 (Artifacts)
- Caption: "All Lab 9 and Lab 10 workflows in one repository"

**Screenshot A2: Code Structure Complete**
- Location: Code tab
- Show: Folder structure:
  ```
  .github/workflows/ (6 files)
  scripts/ (2 files)
  [documentation files]
  ```

**Screenshot A3: Commit History**
- Location: Code → Commits
- Show: Recent commits including:
  - "Lab 10: Add pytest workflows..."
  - Previous lab commits

---

## 📋 SCREENSHOT NAMING CONVENTION

```
Lab10_Ex1_01_Code_Structure.png
Lab10_Ex1_02_Workflow_File.png
Lab10_Ex1_03_Workflow_Run.png
Lab10_Ex1_04_Pytest_Output.png

Lab10_Ex2_01_Matrix_Workflow_File.png
Lab10_Ex2_02_Three_Matrix_Jobs.png
Lab10_Ex2_03_Ubuntu_Job_Logs.png
Lab10_Ex2_04_Windows_Job_Logs.png
Lab10_Ex2_05_MacOS_Job_Logs.png

Lab10_Ex3_01_Exercise3_Workflow_File.png
Lab10_Ex3_02_All_Jobs_Complete.png
Lab10_Ex3_03_Artifacts_Available.png
Lab10_Ex3_04_Download_Artifacts.png
Lab10_Ex3_05_Report_XML_Content.png
Lab10_Ex3_06_Matrix_Speed_Benefit.png

Lab10_Add_01_All_Workflows.png
Lab10_Add_02_Code_Structure_Complete.png
Lab10_Add_03_Commit_History.png
```

---

## 🎥 HOW TO CAPTURE SCREENSHOTS

### Windows 10/11 Built-in Tool
1. Press **Win + Shift + S**
2. Select area to capture
3. Screenshot saves to clipboard
4. Paste into Word/PNG file

### Steps:
1. Navigate to GitHub page showing the feature
2. Press `Win + Shift + S`
3. Click and drag to select area
4. Release to capture
5. Right-click desktop → New → Folder
6. Create "Lab10_Screenshots" folder
7. Paste screenshots there with names

### For scrollable content:
1. Use browser's built-in screenshot (right-click → "Take screenshot")
2. Or scroll and capture multiple times

---

## 📝 PDF REPORT STRUCTURE

### Front Matter
- Title: "Lab 10: More on GitHub Actions"
- Date: [Today's date]
- Student Name: [Your name]

### Exercise 1: Basic Pytest
- Objective
- Code structure (Screenshot 1.1)
- Workflow file (Screenshot 1.2)
- Workflow run (Screenshot 1.3)
- Test output (Screenshot 1.4)
- Summary

### Exercise 2: Matrix Strategy
- Objective
- Workflow file showing matrix (Screenshot 2.1)
- Three jobs running (Screenshot 2.2)
- Ubuntu logs (Screenshot 2.3)
- Windows logs (Screenshot 2.4)
- macOS logs (Screenshot 2.5)
- Benefits of matrix strategy

### Exercise 3: Artifacts
- Objective
- Workflow file with new steps (Screenshot 3.1)
- All jobs complete (Screenshot 3.2)
- Artifacts section (Screenshot 3.3)
- Downloading artifacts (Screenshot 3.4)
- XML report content (Screenshot 3.5)
- Speed comparison (Screenshot 3.6)

### Appendix
- All workflows (Screenshot A1)
- Complete code structure (Screenshot A2)
- Commit history (Screenshot A3)
- All git commands used
- Key concepts explained

---

## ✅ SCREENSHOT CHECKLIST

- [ ] Lab10_Ex1_01_Code_Structure.png
- [ ] Lab10_Ex1_02_Workflow_File.png
- [ ] Lab10_Ex1_03_Workflow_Run.png
- [ ] Lab10_Ex1_04_Pytest_Output.png
- [ ] Lab10_Ex2_01_Matrix_Workflow_File.png
- [ ] Lab10_Ex2_02_Three_Matrix_Jobs.png
- [ ] Lab10_Ex2_03_Ubuntu_Job_Logs.png
- [ ] Lab10_Ex2_04_Windows_Job_Logs.png
- [ ] Lab10_Ex2_05_MacOS_Job_Logs.png
- [ ] Lab10_Ex3_01_Exercise3_Workflow_File.png
- [ ] Lab10_Ex3_02_All_Jobs_Complete.png
- [ ] Lab10_Ex3_03_Artifacts_Available.png
- [ ] Lab10_Ex3_04_Download_Artifacts.png
- [ ] Lab10_Ex3_05_Report_XML_Content.png
- [ ] Lab10_Ex3_06_Matrix_Speed_Benefit.png
- [ ] Lab10_Add_01_All_Workflows.png
- [ ] Lab10_Add_02_Code_Structure_Complete.png
- [ ] Lab10_Add_03_Commit_History.png

**Total: 18 screenshots**

