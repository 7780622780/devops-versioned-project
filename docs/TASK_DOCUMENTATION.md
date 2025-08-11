# TASK 4 - Version Controlled Project Documentation

## Objective
Implement a DevOps project under version control using Git and GitHub best practices. The project must include branch management, pull requests, tags, documentation, and a basic CI workflow.

---

## Tools Used
- **Git** – Version control.
- **GitHub** – Remote repository hosting and collaboration.
- **GitHub Actions** – CI workflow automation.
- **Markdown** – Documentation formatting.
- **Command Line / Git Bash** – Running Git commands.

---

## Repository Structure
devops-versioned-project/
├── .github/
│ └── workflows/
│ └── ci.yml
├── docs/
│ └── TASK_DOCUMENTATION.md
├── screenshots/
├── .gitignore
└── README.md


## Branching Strategy
- **main** – Production-ready branch.
- **dev** – Integration branch for testing features before production.
- **feature/*** – Feature-specific branches for isolated development.
  
Example feature branch: `feature/add-ci`


Step-by-Step Process

 1. Repository Initialization
```bash
mkdir devops-versioned-project
cd devops-versioned-project
git init
Created initial files: README.md, .gitignore.

2. Pushed main branch to GitHub
bash
Copy
Edit
git branch -M main
git remote add origin https://github.com/<username>/devops-versioned-project.git
git push -u origin main

3. Created dev branch
bash
Copy
Edit
git checkout -b dev
git push -u origin dev

4. Created a Feature Branch
bash
Copy
Edit
git checkout -b feature/add-ci
Added .github/workflows/ci.yml with a minimal CI configuration.

5. CI Workflow File
yaml
Copy
Edit
name: CI

on:
  push:
    branches:
      - main
      - dev
      - feature/*
  pull_request:
    branches:
      - main
      - dev

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v3

    - name: Run a test command
      run: echo "✅ GitHub Actions CI is working!"

6. Committed and Pushed Feature Branch
bash
Copy
Edit
git add .github/workflows/ci.yml
git commit -m "feat(ci): add basic GitHub Actions workflow"
git push -u origin feature/add-ci

7. Pull Requests & Merges
Opened PR: feature/add-ci → dev.

Merged PR into dev.

Opened PR: dev → main.

Merged into main.

8. Tagging Release
bash
Copy
Edit
git checkout main
git pull origin main
git tag -a v1.0 -m "v1.0 - First stable submission"
git push origin v1.0
Screenshots
PR Creation – screenshots/pr_creation.png

CI Workflow Success – screenshots/ci_success.png

Branch List – screenshots/branch_list.png

Final Repository Link

https://github.com/7780622780/devops-versioned-project

Learning Outcomes
Understood Git branching and merging strategies.

Learned to create and merge Pull Requests.

Created and configured a GitHub Actions CI workflow.

Used tags to mark stable releases.

Documented the entire process in Markdown.