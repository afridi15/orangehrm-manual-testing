# Test Plan — OrangeHRM Demo

## 1. Objective
Validate the functional correctness of the OrangeHRM demo application across core HR modules through manual and API testing.

## 2. Scope

**In Scope:**
- Login and authentication
- Employee Management (PIM module)
- Leave Management module
- REST API endpoints for employee data

**Out of Scope:**
- Performance testing
- Security penetration testing
- Mobile responsiveness

## 3. Test Environment

| Item | Details |
|------|---------|
| Application URL | https://opensource-demo.orangehrmlive.com |
| Browser | Chrome (latest), Firefox |
| OS | Windows 10, Ubuntu 22.04 |
| API Tool | Postman v10 |
| Credentials | Admin / admin123 |

## 4. Test Types
- Functional Testing
- Boundary Value Analysis
- Negative Testing
- Regression Testing
- API Testing (Postman)

## 5. Entry Criteria
- Application is accessible and demo credentials are working
- Test cases are reviewed and approved

## 6. Exit Criteria
- All critical and high severity test cases executed
- No open critical bugs
- Test summary report completed

## 7. Roles
| Role | Name |
|------|------|
| QA Engineer | Abu Sayeed Md Afridi |

## 8. Deliverables
- Test Cases (test-cases/test_cases.md)
- Bug Reports (bug-reports/bug_report.md)
- Test Summary (README.md)
