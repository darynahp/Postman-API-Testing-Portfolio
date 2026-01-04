# Postman API Testing Portfolio: Conduit App

![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white)

## Project Overview

This project demonstrates a comprehensive automated testing strategy for the **Conduit API**, a real-world example of a blogging platform. The goal of this portfolio is to showcase advanced Postman skills, including collection automation, dynamic variable handling, and robust assertion logic. **Pre-request scripts were extensively used to ensure test independence**, allowing each test to run in isolation with fresh data.

**Tested Application**: [Conduit (Mate Academy Version)](https://conduit.mate.academy/)
**API Documentation**: [Conduit API Specs](https://docs.google.com/spreadsheets/d/1mbRgN4mWt16Pt_9durUiVWfMOQbOjXnckoVnqnPDw1w/edit?gid=0#gid=0)

## 📂 Repository Structure

- **`bugs/`**: Contains detailed XML bug reports for issues found during testing.
- **`conduit_postman_collection.json`**: The core Postman collection file containing all requests, tests, and scripts.
- **`README.md`**: The project documentation file.

## 📊 Testing Statistics

This collection covers critical user flows including authentication, article management, and commenting.

| Metric | Count |
| :--- | :--- |
| **Total Requests** | ~45 |
| **Test Coverage** | Functional, Negative, Security, Status Code, Schema Validation, Response Time |


## ✅ Features Covered

This collection thoroughly tests the following application modules:

*   **User Management**
    *   Registration (Positive flows and validation edge cases).
    *   Authentication (Login with valid/invalid credentials).
    *   User Profile Updates (Bio, image, password).
*   **Articles**
    *   Complete CRUD operations (Create, Read, Update, Delete).
    *   Feed retrieval (Global feed, Personal feed, Tag filtering).
*   **Comments**
    *   Posting and deleting comments.
*   **Profiles**
    *   Following and unfollowing users.
*   **Tags**
    *   Retrieving popular tags.

## 🐞 Key Bugs Discovered

During the testing phase, several critical issues were identified. Below are the detailed bug reports formatted in XML (Jira-style).

### 1. [CON-17] Username Length Validation Failure
**Description**: The API accepts usernames longer than the documented 40-character limit.
- **Severity**: Medium
- **Evidence**: [Watch Video](https://loom.com/i/2df5eb9c18854cc0b7a886952ff1b7b8)
- **Report**: [View XML](./bugs/CON-17_UsernameLength.xml)

### 2. [CON-18] Security Flaw: Unauthorized Article Deletion
**Description**: A critical security vulnerability where a user can delete articles belonging to other users.
- **Severity**: High
- **Evidence**: [Watch Video](https://loom.com/i/84d3e12a61cf4ce486f49ede056446f0)
- **Report**: [View XML](./bugs/CON-18_DeleteOthersArticle.xml)

### 3. [CON-19] Incorrect Status Code for Unauthorized Action
**Description**: Creating an article without authorization returns `401 Unauthorized` instead of the expected `403 Forbidden` (context-dependent) or handled more gracefully.
- **Severity**: Medium
- **Evidence**: [Watch Video](https://loom.com/i/73f3a45f50cf427ba25bb0de48d0d451)
- **Report**: [View XML](./bugs/CON-19_UnauthorizedArticleCreation.xml)

## 🚀 How to Run

1. **Import Collection**:
   - Download `conduit_postman_collection.json`
   - Open Postman -> Import -> Upload the file.

2. **Configure Variables**:
   - The collection includes a `BASE_URL` variable set to `https://conduit.mate.academy/api`.
   - **Important**: The `tokenConduit` variable has been cleared for security. You must run the **Login** request first to automatically populate this token in your collection variables.

3. **Run Automation**:
   - Open the collection runner in Postman.
   - Select the desired folder or the entire collection.
   - Run to see the test results.

---
*Created by Daryna Hopanchuk*
