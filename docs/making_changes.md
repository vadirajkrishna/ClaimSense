# Git Workflow (Solo Project)

This document outlines a simple and effective Git workflow for solo development projects.

---

## 🔹 Principles

- `main` branch should always be **stable and working**
- Use **feature branches** for all development
- Keep commits **small and meaningful**
- Use issues (lightly) to track work

---

## 🔹 Branching Strategy

### 1. Start from `main`

    git checkout main
    git pull origin main

### 2. Create a feature branch

    git checkout -b feature/<feature-name>

Examples:
- `feature/chat-ui`
- `feature/tool-calling`
- `bugfix/streaming-error`

---

## 🔹 Development Workflow

### 3. Work and commit changes

    git add .
    git commit -m "Add streaming chat UI"

Use clear commit messages:
- ✅ `Add SSE streaming for chat`
- ❌ `update code`

---

### 4. Push branch to remote

    git push origin feature/<feature-name>

---

## 🔹 Testing Before Merge (VERY IMPORTANT)

Before merging your feature into `main`, always test:

### 1. Run your application locally

- Ensure app runs without errors  
- Test main flows (e.g., chat, API calls, UI)

---

### 2. Test the specific feature

- Does the feature work as expected?  
- Handle edge cases  
- Check logs for errors  

---

### 3. Run automated tests (if available)

    pytest

or

    python -m unittest

---

### 4. Quick sanity checks

- No broken imports  
- No debug prints/logs left  
- Environment variables/config working  

---

### 5. Optional (recommended)

Merge `main` into your branch before final test:

    git checkout feature/<feature-name>
    git pull origin main

👉 This ensures no conflicts later

---

## 🔹 Merge Workflow

### Option A: Using Pull Request (Recommended)

1. Create a PR on GitHub  
2. Review your own code  
3. Ensure tests pass  
4. Merge into `main`  

---

### Option B: Direct merge

    git checkout main
    git merge feature/<feature-name>
    git push origin main

---

## 🔹 Using Issues (Optional but Recommended)

Create issues for:
- Features  
- Bugs  
- Improvements  

Example:

    #12 Add streaming UI
    #13 Fix tool-calling bug

Reference issues in commits:

    git commit -m "Add streaming UI (#12)"

---

## 🔹 Best Practices

- Keep `main` always deployable  
- Use one branch per feature  
- Avoid large commits  

Delete branches after merge:

    git branch -d feature/<feature-name>

---

## 🔹 Workflow Summary

    main (stable)
       ↓
    feature branch (development)
       ↓
    test thoroughly
       ↓
    merge → main

---

## 🔹 One-line Rule

👉 Never work directly on `main` — always use branches.