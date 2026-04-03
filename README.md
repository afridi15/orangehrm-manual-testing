# OrangeHRM — Manual & API Testing

Manual and API test documentation for [OrangeHRM](https://opensource-demo.orangehrmlive.com),  
an open-source HR management system.

---

## 🔧 Tools Used

| Tool | Purpose |
|------|---------|
| Excel / Google Sheets | Test case documentation |
| Postman | API endpoint testing |
| JIRA (workflow) | Bug tracking & severity classification |
| OrangeHRM Demo | Test target application |

---

## 📁 Project Structure

```
orangehrm-manual-testing/
├── test-plan/
│   └── test_plan.docx
├── test-cases/
│   └── test_cases.xlsx
├── bug-reports/
│   └── bug_report.xlsx
└── README.md
```

---

## ✅ Modules Covered

- **Login** — valid/invalid credentials, session handling
- **Employee Management** — add, edit, delete employee records
- **Leave Module** — apply, approve, reject leave requests
- **API Endpoints** — authentication, employee data via Postman

---

## 📊 Test Summary

| Module | Test Cases | Passed | Failed | Blocked |
|--------|-----------|--------|--------|---------|
| Login | 12 | 10 | 2 | 0 |
| Employee Management | 20 | 17 | 2 | 1 |
| Leave Module | 18 | 15 | 3 | 0 |
| **Total** | **50** | **42** | **7** | **1** |

---

## 🐛 Bug Tracking

Bugs documented in `bug-reports/bug_report.xlsx` with:
- Bug ID, Title, Module
- Steps to reproduce
- Expected vs Actual result
- Severity & Priority
- Status
