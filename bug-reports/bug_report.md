# Bug Reports — OrangeHRM Demo

---

## BUG-001

| Field | Details |
|-------|---------|
| **Bug ID** | BUG-001 |
| **Title** | Invalid file format accepted as profile photo |
| **Module** | Employee Management |
| **Related TC** | TC_EMP_009 |
| **Severity** | Medium |
| **Priority** | Medium |
| **Status** | Open |

**Steps to Reproduce:**
1. Log in as Admin
2. Go to PIM > Employee List > Open any employee
3. Click on the profile photo area
4. Upload a `.txt` file

**Expected Result:** Error message: "Invalid file format. Please upload an image."

**Actual Result:** File is silently ignored with no error message shown to the user.

---

## BUG-002

| Field | Details |
|-------|---------|
| **Bug ID** | BUG-002 |
| **Title** | Overlapping leave request not prevented |
| **Module** | Leave Management |
| **Related TC** | TC_LVE_003 |
| **Severity** | High |
| **Priority** | High |
| **Status** | Open |

**Steps to Reproduce:**
1. Log in as an employee
2. Apply for Annual Leave on 2025-08-01 to 2025-08-03
3. After approval, apply again for Annual Leave on 2025-08-02 to 2025-08-04

**Expected Result:** Error: "You already have a leave request for these dates."

**Actual Result:** Second request is created successfully, resulting in duplicate/overlapping leave records.

---

## BUG-003

| Field | Details |
|-------|---------|
| **Bug ID** | BUG-003 |
| **Title** | No warning when applying leave on a public holiday |
| **Module** | Leave Management |
| **Related TC** | TC_LVE_014 |
| **Severity** | Low |
| **Priority** | Low |
| **Status** | Open |

**Steps to Reproduce:**
1. Log in as an employee
2. Ensure a public holiday is configured in Admin > Leave > Holidays
3. Apply for leave on that public holiday date

**Expected Result:** A warning or informational message: "This date is a public holiday."

**Actual Result:** Leave is submitted with no warning. User is unaware they are applying on a holiday.

---

## Bug Summary

| Bug ID | Module | Severity | Priority | Status |
|--------|--------|----------|----------|--------|
| BUG-001 | Employee Management | Medium | Medium | Open |
| BUG-002 | Leave Management | High | High | Open |
| BUG-003 | Leave Management | Low | Low | Open |
