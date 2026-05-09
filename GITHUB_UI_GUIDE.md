# GitHub UI Guide & Screenshots Checklist

## WHERE TO FIND EVERYTHING ON GITHUB

---

## 1. ACTIONS TAB - Where Workflows Run

### Location:
- Your repository URL: `https://github.com/YOUR_USERNAME/github-actions-lab`
- Click the **"Actions"** tab in the top navigation

### What You'll See:
- List of all workflows (hello.yml, dev-branch.yml, advanced.yml)
- Each workflow shows all runs
- Yellow dot = Running
- Green checkmark = Success
- Red X = Failed

### How to View Workflow Details:
1. Click on "Actions" tab
2. Click on a workflow name on the left sidebar
3. Click on a specific run (shows timestamp and commit)
4. View the job status
5. Click on the job name to expand steps
6. Each step shows input and output

---

## 2. WORKFLOW LOGS - Where Output Appears

### Location:
- Repository → Actions → [Workflow Name] → [Run ID]

### What Shows Here:
- **Step-by-step execution**
- **Command output** (echo messages)
- **Errors** (if any)
- **Python version** (for Exercise 3)
- **Count output** (for Exercise 3)
- **Installed packages** (for Exercise 3)

### Example Output to Look For:
```
Run echo "Hello from GitHub Actions!"
Hello from GitHub Actions!
```

```
Run python --version
Python 3.10.x
```

```
Run python -c "
Starting counter...
Count: 1
Count: 2
Count: 3
Count: 4
Count: 5
Counter completed!
```

---

## 3. PULL REQUEST STATUS CHECKS

### Location:
- Repository → Pull Requests → [Your PR Name]

### What You'll See:
- **"All checks passed"** or **"Some checks failed"** message
- Status checks from workflows
- Each workflow appears as a status check
- ✅ for passed, ❌ for failed, ⏳ for running

### How to View Details:
1. In the PR, scroll down to "Checks" section
2. Click on a check to expand details
3. Click "Details" link to view full logs

---

## 4. CODE TAB - Viewing Files

### Location:
- Repository → Code tab (default view)

### What You'll See:
- All repository files and folders
- `.github/workflows/` folder
- All three workflow files:
  - `hello.yml`
  - `dev-branch.yml`
  - `advanced.yml`
- `README.md` file

### How to View File Content:
1. Click on `.github` folder
2. Click on `workflows` folder
3. Click on any `.yml` file
4. View the YAML code

---

## 5. BRANCHES TAB - Managing Branches

### Location:
- Repository → Code → Branches tab (or main button dropdown)

### What You'll See:
- `main` branch (default)
- `dev` branch (after Exercise 2)
- Branch comparison
- Number of commits ahead/behind
- Last commit date

### Delete a Branch:
- Click trash icon next to branch name

---

## 6. COMMITS VIEW - Seeing What Changed

### Location:
- Repository → [Branch Name] → Commit History

### What You'll See:
- Each commit with timestamp
- Commit message
- Author name
- Files changed (green = added, red = deleted)

### View Specific Commit:
- Click on commit hash to see diff
- Shows line-by-line changes

---

## 7. INSIGHTS → NETWORK GRAPH - Visualizing Branches

### Location:
- Repository → Insights → Network

### What You'll See:
- Visual graph of all branches
- How branches merge
- Timeline of commits
- Parallel development lines

### Great For:
- Understanding merge history
- Seeing which commits are on which branches
- Identifying diverged branches

---

## SCREENSHOTS CHECKLIST FOR PDF DELIVERABLE

### ✅ EXERCISE 1 Screenshots

**Screenshot 1.1**: Initial Repository Setup
- GitHub repo URL showing "github-actions-lab"
- Files visible in Code tab
- `.github/workflows/` folder visible

**Screenshot 1.2**: First Workflow File
- Open `hello.yml` file in GitHub
- Show YAML code displayed
- Content clearly visible

**Screenshot 1.3**: First Workflow Run
- Actions tab showing workflow runs
- Green checkmark next to first run
- Show the run timestamp

**Screenshot 1.4**: Workflow Logs Output
- Click on the run → view logs
- Show the step "Print Hello Message"
- **Capture output**: "Hello from GitHub Actions!"

---

### ✅ EXERCISE 2 Screenshots

**Screenshot 2.1**: Dev Branch Created
- Branches tab
- Show `main` and `dev` branches
- Both branches visible

**Screenshot 2.2**: Updated Workflow File
- Open `dev-branch.yml` in GitHub
- Show the trigger configuration:
  ```yaml
  on:
    push:
      branches: [ dev ]
    pull_request:
      branches: [ main ]
  ```

**Screenshot 2.3**: Pull Request Created
- Pull requests tab
- Show PR with title like "Add Exercise 2 workflow"
- Show "Open" status

**Screenshot 2.4**: Status Checks on PR
- Same PR page, scroll down
- Show "Checks" section
- Status checks appearing (green or yellow)
- Show workflow name(s)

**Screenshot 2.5**: PR Status Check Details
- Click "Details" on a status check
- Show workflow logs appearing for the PR

**Screenshot 2.6**: Workflow Run from Dev Branch Push
- Actions tab
- Show workflow triggered by "push" event
- Show branch name: "dev"

**Screenshot 2.7**: PR Merge and Confirmation
- PR page showing "Merge pull request" button
- After merge: show merge confirmation message

---

### ✅ EXERCISE 3 Screenshots

**Screenshot 3.1**: Advanced Workflow File
- Open `advanced.yml` file
- Show Python setup section:
  ```yaml
  - uses: actions/setup-python@v5
    with:
      python-version: '3.10'
  ```

**Screenshot 3.2**: Workflow Run in Progress
- Actions tab
- Show workflow running (yellow/blue status)
- Show multiple steps listed

**Screenshot 3.3**: Python Version Output
- Workflow run logs
- Expand "Set up Python" step
- Show output: `Python 3.10.x`

**Screenshot 3.4**: Counting Script Output
- Same workflow logs
- Expand "Run Counting Script" step
- **Capture all output**:
  ```
  Starting counter...
  Count: 1
  Count: 2
  Count: 3
  Count: 4
  Count: 5
  Counter completed!
  ```

**Screenshot 3.5**: Package Installation Output
- Expand "Install Example Package" step
- Show pip install process

**Screenshot 3.6**: Requests Library Version
- Expand "Verify Installation" step
- Show: `Requests library version: x.x.x`

**Screenshot 3.7**: Full Workflow Summary
- After all steps complete
- Show green checkmark
- Show "Completed successfully" message
- Show total execution time

---

### ✅ ADDITIONAL IMPORTANT SCREENSHOTS

**Screenshot A1**: Network Graph
- Insights → Network
- Show branch visualization
- Show merge commits

**Screenshot A2**: Complete File Structure
- Code tab showing folder hierarchy
- `.github/workflows/` with all three `.yml` files
- `README.md` file visible

**Screenshot A3**: All Three Workflows Listed
- Actions tab left sidebar
- Show all three workflow names:
  - Exercise 1 - Hello GitHub Actions
  - Exercise 2 - Dev Branch & Pull Requests
  - Exercise 3 - Advanced Python Workflow

**Screenshot A4**: Commit History
- Commits tab
- Show several commits with messages

---

## STEPS TO CAPTURE EACH SCREENSHOT

### For Workflow Logs:
1. Go to Actions tab
2. Click workflow name
3. Click the specific run (by date/time)
4. Click the job name to expand steps
5. Expand individual steps to show output
6. Use Print Screen or Snip & Sketch tool
7. Save as: `screenshot_exercise_X_description.png`

### For PR and Branches:
1. Go to Pull Requests tab
2. Click the PR
3. Scroll to see different sections
4. Use Print Screen to capture full PR view

### For Code Files:
1. Go to Code tab
2. Navigate to `.github/workflows/`
3. Click on `.yml` file to view
4. Take screenshot of file content

### Using Windows Snip & Sketch:
- Press `Win + Shift + S`
- Select area to capture
- Screenshot saved to clipboard
- Paste into Word/PDF editor

---

## NAMING CONVENTION FOR SCREENSHOTS

```
Ex1_01_Repository_Setup.png
Ex1_02_hello_yml_File.png
Ex1_03_Workflow_Run_Success.png
Ex1_04_Logs_Hello_Output.png

Ex2_01_Dev_Branch_Created.png
Ex2_02_dev-branch_yml_File.png
Ex2_03_Pull_Request_Created.png
Ex2_04_Status_Checks_on_PR.png
Ex2_05_Status_Check_Details.png
Ex2_06_Workflow_Run_Event_Push.png
Ex2_07_PR_Merged.png

Ex3_01_advanced_yml_File.png
Ex3_02_Workflow_Running.png
Ex3_03_Python_Version_Output.png
Ex3_04_Counting_Script_Output.png
Ex3_05_Package_Installation.png
Ex3_06_Requests_Library_Version.png
Ex3_07_Complete_Workflow_Success.png

Add_01_Network_Graph.png
Add_02_File_Structure.png
Add_03_All_Workflows_Listed.png
Add_04_Commit_History.png
```

---

## PDF DELIVERABLE ORGANIZATION

```
📄 GitHub Actions Lab - Final Report

1. Introduction
   - Project overview
   - 3 exercises covered

2. Exercise 1: Hello GitHub Actions
   - Step 1: Initialize git
   - Step 2: Set up repository
   - Step 3: First push triggers workflow
   - Screenshots: 1.1, 1.2, 1.3, 1.4
   - Show git commands used

3. Exercise 2: Dev Branch & Pull Requests
   - Step 1: Create dev branch
   - Step 2: Push to dev
   - Step 3: Create pull request
   - Step 4: See status checks
   - Screenshots: 2.1 through 2.7
   - Show git commands used
   - Explain triggers

4. Exercise 3: Advanced Python Workflow
   - Step 1: Set up Python environment
   - Step 2: Install packages
   - Step 3: Run Python scripts
   - Screenshots: 3.1 through 3.7
   - Show git commands used
   - Explain advanced features

5. Conclusion
   - Summary of what was learned
   - Additional resources

6. Appendix
   - Complete YAML files
   - All git commands reference
   - Screenshots: Add_01 through Add_04
```

