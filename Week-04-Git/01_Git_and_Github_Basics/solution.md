# Week 4 – Git & GitHub Solution

## Git Commands Used in Tasks 1–4

### Task 1 – Initialize Repository
git init
git add .
git commit -m "Initial commit"

### Task 2 – Configure Remote Repository
git remote add origin https://github.com/byteaagam/90DaysOfDevOps.git
git branch -M main
git push -u origin main

### Task 3 – Configure PAT Authentication
git remote -v
git push
git pull
git branch --set-upstream-to=origin/main main

### Task 4 – Feature Branch Workflow
git checkout -b feature-update
git add info.txt
git commit -m "Feature update"
git push -u origin feature-update
git checkout main
git merge feature-update

---

## Why Branching Strategies Are Important

Branching strategies are crucial in collaborative development because:

### 1. Isolating Features and Bug Fixes
Branches allow developers to work on new features or bug fixes without affecting the stable main branch.

### 2. Facilitating Parallel Development
Multiple developers can work simultaneously on different features using separate branches.

### 3. Reducing Merge Conflicts
Since work is isolated in branches, conflicts are minimized and easier to resolve.

### 4. Enabling Effective Code Reviews
Branches enable Pull Requests, allowing teams to review code before merging into the main branch.