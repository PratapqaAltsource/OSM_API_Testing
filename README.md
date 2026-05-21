# OSM_API-Testing

# OSM — Online Script Marking System

A web-based platform for end-to-end digital management of answer script evaluation — from scanning physical answer sheets to final result generation. OSM eliminates manual handling by digitizing the entire marking workflow across four role-based modules.

---

## 🎯 Objective

To streamline the answer script evaluation process by enabling online scanning, intelligent evaluator assignment, digital marking, multi-level validation, and result reporting — ensuring accuracy, transparency, and efficiency at every stage.

---

## 🧩 Modules

### 1. 🖨️ Scanner
Handles the digitization of physical answer scripts and question papers.
- Scan and upload question papers
- Slice question paper into individual questions
- Upload answer sheets for digital processing

### 2. ✏️ Evaluator
Subject-qualified evaluators review and mark answer sheets online.
- View assigned answer sheets
- Mark / remark scripts digitally
- Submit evaluated scripts for validation

### 3. 🛡️ Validator
Acts as a quality check layer after evaluator marking.
- Review evaluator-marked scripts
- Validate or flag scripts
- Forward validated scripts to Admin for final decision

### 4. ⚙️ Admin Module
Central control panel managing the entire workflow.
- Add and manage evaluators
- Assign scripts based on evaluator qualification
- Decide on reassignment / rechecking after validator review
- View allocation status and results
- Generate reports

---

## 🔄 Workflow

```
Scanner → Upload Answersheet
    ↓
Admin → Assign Script to Evaluator (by qualification)
    ↓
Evaluator → Mark Answersheet Online
    ↓
Validator → Validate Marked Script
    ↓
Admin → Approve  OR  Reassign for Rechecking
    ↓
Results Generated
```

---

## 🧪 API Test Summary (Admin Module)

> Tested with **Newman** | Date: `2026-05-19`

| Total Requests | Failed Tests | Auth | Base URL |
|---|---|---|---|
| 20 | 0 ✅ | Bearer JWT | `http://<host>:5000` |

### Admin Module Structure

```
Admin Module
├── Admin Login
├── Dashboard
├── Evaluator Management
│   ├── Evaluator Onboarding
│   ├── Assign Scripts
│   └── User Management (View / Add Users)
├── Exam Management
│   ├── Subjects (CRUD)
│   ├── Create / Configure Exam
│   ├── View Exams
│   ├── Upload QP & Marking Scheme
│   └── Results
└── Reports & Analytics
    ├── Overview / Evaluator Stats
    ├── Evaluator Allocations
    └── Daily Scanning & Validations
```

---

## 🚀 Run API Tests

```bash
npm install -g newman newman-reporter-htmlextra

newman run OSM_API_AdminModule.postman_collection \
  -r htmlextra \
  --reporter-htmlextra-export report.html
```
