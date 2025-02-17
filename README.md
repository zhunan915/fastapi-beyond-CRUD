# 🚀 FastAPI Beyond CRUD - Conventional Commits & Semantic Versioning (SemVer) Validation  

This repository includes a **GitHub Actions Workflow** that enforces **Conventional Commits** and **Semantic Versioning (SemVer)** for all **Pull Requests (PRs).**  

For more details on FastAPI Beyond CRUD, visit the project's [website](https://jod35.github.io/fastapi-beyond-crud-docs/site/).

---

## 📌 Table of Contents

1. [Overview](#overview)  
2. [Features](#features)  
3. [Setup Instructions](#setup-instructions)  
4. [Testing Conventional Commit Validations](#testing-conventional-commit-validations)  
   - [Testing Bad PR Title](#1-testing-bad-pr-title)  
        - [Screenshots](#screenshots)  
   - [Testing Bad Commit Message](#2-testing-bad-commit-message)  
        - [Screenshots](#screenshots)  
   - [Testing Bad Commit Body](#3-testing-bad-commit-body)  
        - [Screenshots](#screenshots)  
5. [Testing Nightly Build & Docker Deployment](#testing-nightly-build--docker-deployment)  
6. [Run Application](#run-docker-entire-app)


---

## 📌 Overview

This project ensures that all pull requests comply with **Conventional Commits** and **Semantic Versioning (SemVer)** using **GitHub Actions**.  

It includes:  
✅ PR Title Validation  
✅ Commit Message Validation  
✅ PR Auto-Closure if validation fails  
✅ Email Notification on failure  
✅ Nightly Build & Docker Deployment  

---

## 🔹 Features

- **PR Title Validation**: Ensures PR titles follow the **Conventional Commit** format.
- **Commit Message Validation**: Every commit in a PR must adhere to **Conventional Commit & SemVer**.
- **PR Auto-Closure**: If a PR fails the validation, it is **automatically closed**.
- **Email Notification**: An email is sent to notify the user when a PR fails the validation.
- **Nightly Build**: Runs tests and builds the Docker image at **12 AM UTC**. If tests fail, the image is not pushed.

---

## 🔹 Setup Instructions  

### 1️⃣ **Move Required GitHub Secrets to .env**  

To prevent exposing credentials, simply run
```sh
    cp .env.example .env
```


---

## 🔹 Testing Conventional Commit Validations  

### 📌 **1. Testing Bad PR Title**  

1. **Make a commit**:
```sh
    echo "Add new test file" > test.txt
    git add test.txt
    git commit -m "feat: add login functionality"
    git push origin test-bad-pr-title
```
Here is a screenshot showing the PR failure after a bad PR title:

![PR Failure Screenshot](./screenshots/test-bad-pr-title.png)
![PR Failure Screenshot](./screenshots/bad-pr-title-2.png)
![PR Failure Screenshot](./screenshots/bad-pr-title-3.jpg)
![PR Failure Screenshot](./screenshots/bad-title-4.jpg)

### 📌 **2. Testing Bad Commit Message**

1. **Make a commit with an invalid message**:
```sh
    echo "Testing bad commit message" > test.txt
    git add test.txt
    git commit -m "Updated something"
    git push origin test-bad-commit
```

Here is a screenshot showing the PR failure after a bad commit message:

![PR Failure Screenshot](./screenshots/bad-commit-message-1.png)
![PR Failure Screenshot](./screenshots/bad-commit-message-2.png)

### 📌 **3. Testing Bad Commit Body*

1. **Make a commit with an invalid body**:
```sh
    echo "Testing bad commit body" > test.txt
    git add test.txt
    git commit -m "feat: add login functionality" -m "Some random message without proper description."
    git push origin test-bad-commit-body
```

Here is a screenshot showing the PR failure after a bad commit message:

![PR Failure Screenshot](./screenshots/bad-commit-message-1.png)
![PR Failure Screenshot](./screenshots/bad-commit-message-2.png)

