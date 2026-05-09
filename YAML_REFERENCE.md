# Complete YAML Workflow Files - Ready to Copy

## ⚠️ Important Notes:
- YAML is **whitespace-sensitive** - indentation must be exactly correct
- Use **spaces, not tabs** (2-space indentation standard)
- File must end with `.yml` or `.yaml`
- Location: `.github/workflows/` folder
- No special characters in file names (use hyphens, not underscores for readability)

---

## EXERCISE 1: hello.yml

**File Location**: `.github/workflows/hello.yml`

**Triggers**: Every push to any branch

**What it does**: Prints "Hello from GitHub Actions!" message

```yaml
name: Exercise 1 - Hello GitHub Actions

on:
  push

jobs:
  hello:
    runs-on: ubuntu-latest
    
    steps:
      - name: Print Hello Message
        run: echo "Hello from GitHub Actions!"
```

### Copy-Paste Version (Plain Text):
```
name: Exercise 1 - Hello GitHub Actions

on:
  push

jobs:
  hello:
    runs-on: ubuntu-latest
    
    steps:
      - name: Print Hello Message
        run: echo "Hello from GitHub Actions!"
```

---

## EXERCISE 2: dev-branch.yml

**File Location**: `.github/workflows/dev-branch.yml`

**Triggers**: 
- Push to `dev` branch
- Pull requests targeting `main` branch

**What it does**: 
- Checks out your code
- Prints workflow information (branch name, event type)

```yaml
name: Exercise 2 - Dev Branch & Pull Requests

on:
  push:
    branches: [ dev ]
  pull_request:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest
    
    steps:
      - name: Checkout Code
        uses: actions/checkout@v4
      
      - name: Print Workflow Info
        run: |
          echo "Workflow triggered!"
          echo "Branch: ${{ github.ref }}"
          echo "Event: ${{ github.event_name }}"
```

### Copy-Paste Version (Plain Text):
```
name: Exercise 2 - Dev Branch & Pull Requests

on:
  push:
    branches: [ dev ]
  pull_request:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest
    
    steps:
      - name: Checkout Code
        uses: actions/checkout@v4
      
      - name: Print Workflow Info
        run: |
          echo "Workflow triggered!"
          echo "Branch: ${{ github.ref }}"
          echo "Event: ${{ github.event_name }}"
```

---

## EXERCISE 3: advanced.yml

**File Location**: `.github/workflows/advanced.yml`

**Triggers**:
- Push to `dev` or `main` branches
- Pull requests targeting `main` branch

**What it does**:
- Sets up Python 3.10
- Prints welcome message
- Shows Python version
- Runs a counting loop (1-5)
- Installs the `requests` library
- Verifies the installation

```yaml
name: Exercise 3 - Advanced Python Workflow

on:
  push:
    branches: [ dev, main ]
  pull_request:
    branches: [ main ]

jobs:
  python-job:
    runs-on: ubuntu-latest
    
    steps:
      - name: Checkout Code
        uses: actions/checkout@v4
      
      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.10'
      
      - name: Print Welcome Message
        run: echo "Welcome to Advanced GitHub Actions with Python!"
      
      - name: Print Python Version
        run: python --version
      
      - name: Run Counting Script
        run: |
          python -c "
          print('Starting counter...')
          for i in range(1, 6):
              print(f'Count: {i}')
          print('Counter completed!')
          "
      
      - name: Install Example Package
        run: pip install requests
      
      - name: Verify Installation
        run: python -c "import requests; print(f'Requests library version: {requests.__version__}')"
```

### Copy-Paste Version (Plain Text):
```
name: Exercise 3 - Advanced Python Workflow

on:
  push:
    branches: [ dev, main ]
  pull_request:
    branches: [ main ]

jobs:
  python-job:
    runs-on: ubuntu-latest
    
    steps:
      - name: Checkout Code
        uses: actions/checkout@v4
      
      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.10'
      
      - name: Print Welcome Message
        run: echo "Welcome to Advanced GitHub Actions with Python!"
      
      - name: Print Python Version
        run: python --version
      
      - name: Run Counting Script
        run: |
          python -c "
          print('Starting counter...')
          for i in range(1, 6):
              print(f'Count: {i}')
          print('Counter completed!')
          "
      
      - name: Install Example Package
        run: pip install requests
      
      - name: Verify Installation
        run: python -c "import requests; print(f'Requests library version: {requests.__version__}')"
```

---

## YAML QUICK REFERENCE

### Key Terms Explained:

| Term | Meaning |
|------|---------|
| `name:` | Display name shown in Actions tab |
| `on:` | Events that trigger the workflow |
| `push:` | Trigger on code push |
| `pull_request:` | Trigger on PR creation/update |
| `branches: [ dev ]` | Only trigger on this branch |
| `jobs:` | Container for all jobs |
| `runs-on:` | Which machine to use (ubuntu-latest, windows-latest, etc.) |
| `steps:` | List of commands to execute |
| `name:` | Description of what the step does |
| `run:` | Shell command to execute |
| `uses:` | GitHub Action to use |
| `with:` | Parameters for the action |

### Indentation Rules:

```yaml
name: My Workflow          # No indentation
on:                        # No indentation
  push:                    # 2-space indent (under 'on')
    branches: [ main ]     # 4-space indent (under 'push')
jobs:                      # No indentation
  my-job:                  # 2-space indent
    runs-on: ubuntu-latest # 4-space indent
    steps:                 # 4-space indent
      - name: My Step      # 6-space indent
        run: echo "hi"     # 8-space indent
```

---

## COMMON GITHUB ACTIONS

### Check Out Code
```yaml
- name: Checkout Code
  uses: actions/checkout@v4
```

### Set Up Python
```yaml
- name: Set up Python
  uses: actions/setup-python@v5
  with:
    python-version: '3.10'
```

### Set Up Node.js
```yaml
- name: Set up Node.js
  uses: actions/setup-node@v4
  with:
    node-version: '18'
```

### Run a Shell Command
```yaml
- name: Run Command
  run: echo "Hello World"
```

### Run Python Script
```yaml
- name: Run Python
  run: python script.py
```

### Install Python Packages
```yaml
- name: Install Dependencies
  run: pip install -r requirements.txt
```

---

## ENVIRONMENT VARIABLES IN WORKFLOWS

### Built-in Variables:

```yaml
- name: Show GitHub Variables
  run: |
    echo "Branch: ${{ github.ref }}"
    echo "Event: ${{ github.event_name }}"
    echo "Actor: ${{ github.actor }}"
    echo "Commit: ${{ github.sha }}"
```

### Custom Variables:

```yaml
env:
  CUSTOM_VAR: "my-value"

jobs:
  my-job:
    runs-on: ubuntu-latest
    steps:
      - name: Use Variable
        run: echo $CUSTOM_VAR
```

---

## TROUBLESHOOTING YAML SYNTAX

### ❌ Wrong Indentation
```yaml
name: My Workflow
jobs:
my-job:          # WRONG - needs 2-space indent
  runs-on: ubuntu-latest
```

### ✅ Correct Indentation
```yaml
name: My Workflow
jobs:
  my-job:        # CORRECT - 2-space indent
    runs-on: ubuntu-latest
```

### ❌ Tabs Instead of Spaces
```yaml
jobs:
	my-job:      # WRONG - uses tab (GitHub won't parse)
```

### ✅ Use Spaces
```yaml
jobs:
  my-job:        # CORRECT - uses spaces
```

### ❌ Missing Colon
```yaml
on push          # WRONG
```

### ✅ Include Colon
```yaml
on:              # CORRECT
  push
```

### ❌ Unquoted Multiline
```yaml
run: echo "Hello
       World"    # WRONG - breaks the syntax
```

### ✅ Use Pipe for Multiline
```yaml
run: |           # CORRECT - pipe allows multiline
  echo "Hello"
  echo "World"
```

---

## VALIDATE YOUR YAML

**Online YAML Validator**: https://yamllint.com/

1. Copy your workflow YAML
2. Paste into the validator
3. It will show any syntax errors
4. Fix errors before pushing to GitHub

---

## QUICK GIT COMMANDS FOR THIS LAB

```bash
# Initial setup
git init
git config user.name "Your Name"
git config user.email "your@email.com"
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/USERNAME/github-actions-lab.git
git branch -M main
git push -u origin main

# Work on dev branch
git checkout -b dev
git push -u origin dev

# After making changes
git add .
git commit -m "Your message"
git push origin dev

# Create pull request (on GitHub website)
# Then merge and sync back
git checkout main
git pull origin main
```

---

## WHEN TO USE EACH WORKFLOW

### Exercise 1 (hello.yml)
- **When**: Learning the basics
- **Use**: Testing simple echoed output
- **Triggers**: Every push (no filtering)

### Exercise 2 (dev-branch.yml)
- **When**: Learning branches and PRs
- **Use**: Development workflows
- **Triggers**: Dev branch OR PR to main

### Exercise 3 (advanced.yml)
- **When**: Learning real-world workflows
- **Use**: Running actual Python code
- **Triggers**: Dev/main pushes OR PRs to main

---

## NEXT STEPS AFTER COMPLETING LAB

1. **Add test script**:
   ```yaml
   - name: Run Tests
     run: pytest tests/
   ```

2. **Add code coverage**:
   ```yaml
   - name: Coverage Report
     run: coverage run -m pytest
   ```

3. **Deploy to GitHub Pages**:
   ```yaml
   - name: Deploy
     uses: peaceiris/actions-gh-pages@v3
   ```

4. **Notify on failure**:
   ```yaml
   - name: Send Alert
     if: failure()
     run: echo "Workflow failed!"
   ```

5. **Use secrets** (passwords, tokens):
   ```yaml
   - name: Use Secret
     run: echo ${{ secrets.MY_SECRET }}
   ```

