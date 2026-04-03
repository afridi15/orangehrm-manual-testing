# Test Cases — OrangeHRM Demo

---

## Module: Login

| TC ID | Title | Precondition | Steps | Expected Result | Actual Result | Status |
|-------|-------|-------------|-------|----------------|--------------|--------|
| TC_LOG_001 | Valid login | App is open | Enter Admin/admin123, click Login | Redirect to Dashboard | As expected | Pass |
| TC_LOG_002 | Invalid username | App is open | Enter wrongUser/admin123, click Login | Error: "Invalid credentials" | As expected | Pass |
| TC_LOG_003 | Invalid password | App is open | Enter Admin/wrongPass, click Login | Error: "Invalid credentials" | As expected | Pass |
| TC_LOG_004 | Empty username | App is open | Leave username blank, click Login | Error: "Required" | As expected | Pass |
| TC_LOG_005 | Empty password | App is open | Leave password blank, click Login | Error: "Required" | As expected | Pass |
| TC_LOG_006 | Empty both fields | App is open | Leave both blank, click Login | Validation errors on both fields | As expected | Pass |
| TC_LOG_007 | SQL injection in username | App is open | Enter `' OR 1=1 --` as username | Login rejected, no DB error exposed | As expected | Pass |
| TC_LOG_008 | Logout | Logged in | Click username > Logout | Redirect to login page | As expected | Pass |
| TC_LOG_009 | Session expiry | Logged in | Wait for session timeout, try navigating | Redirect to login page | As expected | Pass |
| TC_LOG_010 | Remember me (if present) | App is open | Check Remember Me, login, close browser, reopen | User stays logged in | Feature not present | Blocked |
| TC_LOG_011 | Case sensitivity username | App is open | Enter ADMIN/admin123 | Login rejected | As expected | Pass |
| TC_LOG_012 | Special characters password | App is open | Enter Admin/!@#$%^, click Login | Login rejected with error | As expected | Pass |

---

## Module: Employee Management (PIM)

| TC ID | Title | Precondition | Steps | Expected Result | Actual Result | Status |
|-------|-------|-------------|-------|----------------|--------------|--------|
| TC_EMP_001 | Add new employee | Logged in as Admin | Go to PIM > Add Employee, fill all fields, Save | Employee created successfully | As expected | Pass |
| TC_EMP_002 | Add employee — missing required field | Logged in | Leave First Name blank, click Save | Validation error shown | As expected | Pass |
| TC_EMP_003 | Search employee by name | Employee exists | Go to PIM > Employee List, search by name | Matching employee shown | As expected | Pass |
| TC_EMP_004 | Search non-existent employee | Logged in | Search for "ZZZNOBODY" | "No Records Found" message | As expected | Pass |
| TC_EMP_005 | Edit employee details | Employee exists | Open employee > Edit > change job title > Save | Changes saved | As expected | Pass |
| TC_EMP_006 | Delete employee | Employee exists | Select employee > Delete > Confirm | Employee removed from list | As expected | Pass |
| TC_EMP_007 | Delete employee — cancel | Employee exists | Select > Delete > Cancel | Employee not deleted | As expected | Pass |
| TC_EMP_008 | Upload profile photo | Employee exists | Open employee > upload image > Save | Photo displayed | As expected | Pass |
| TC_EMP_009 | Upload invalid file format | Employee exists | Upload .txt as profile photo | Error: invalid file type | Error not shown, file ignored | Fail |
| TC_EMP_010 | Employee ID uniqueness | Logged in | Create employee with existing ID | Error: ID already in use | As expected | Pass |
| TC_EMP_011 | Add employee — max name length | Logged in | Enter 100 character first name | Accepted or validation shown | Accepted without truncation | Pass |
| TC_EMP_012 | Filter employees by department | Employees exist | Filter by HR department | Only HR employees shown | As expected | Pass |
| TC_EMP_013 | Filter employees by status | Employees exist | Filter by Active status | Only active employees shown | As expected | Pass |
| TC_EMP_014 | Pagination on employee list | 15+ employees | Navigate to page 2 | Next set of employees shown | As expected | Pass |
| TC_EMP_015 | Sort employee list by name | Employees exist | Click Name column header | List sorted alphabetically | As expected | Pass |
| TC_EMP_016 | View employee profile | Employee exists | Click on employee name | Full profile displayed | As expected | Pass |
| TC_EMP_017 | Add emergency contact | Employee exists | Go to Emergency Contacts tab > Add > Save | Contact saved | As expected | Pass |
| TC_EMP_018 | Add work experience | Employee exists | Go to Work Experience > Add > Save | Experience saved | As expected | Pass |
| TC_EMP_019 | Add education | Employee exists | Go to Qualifications > Education > Save | Education entry saved | As expected | Pass |
| TC_EMP_020 | Bulk delete employees | Multiple employees | Select 3 > Delete | All 3 removed | As expected | Pass |

---

## Module: Leave Management

| TC ID | Title | Precondition | Steps | Expected Result | Actual Result | Status |
|-------|-------|-------------|-------|----------------|--------------|--------|
| TC_LVE_001 | Apply for annual leave | Logged in as employee | Go to Leave > Apply, select dates, submit | Leave request submitted | As expected | Pass |
| TC_LVE_002 | Apply leave — past date | Logged in | Select a past date, submit | Error: cannot apply for past dates | As expected | Pass |
| TC_LVE_003 | Apply leave — overlapping dates | Leave already exists | Apply for same date again | Error: overlapping leave | Error not shown, duplicate created | Fail |
| TC_LVE_004 | Admin approves leave | Leave request pending | Go to Leave > Leave List, click Approve | Status changes to Approved | As expected | Pass |
| TC_LVE_005 | Admin rejects leave | Leave request pending | Click Reject, add reason | Status changes to Rejected | As expected | Pass |
| TC_LVE_006 | Employee cancels pending leave | Leave pending | Go to My Leave, click Cancel | Leave cancelled | As expected | Pass |
| TC_LVE_007 | Leave balance check | Logged in | Go to My Leave > Entitlements | Correct balance shown | As expected | Pass |
| TC_LVE_008 | Apply leave exceeding balance | Logged in | Apply for more days than balance | Error: insufficient balance | As expected | Pass |
| TC_LVE_009 | Apply half-day leave | Logged in | Select half-day option, submit | Half-day leave created | As expected | Pass |
| TC_LVE_010 | Leave report generation | Logged in as Admin | Go to Reports > Leave, generate | Report downloaded/displayed | As expected | Pass |
| TC_LVE_011 | Filter leave by type | Logged in as Admin | Filter by Annual Leave | Only annual leave shown | As expected | Pass |
| TC_LVE_012 | Filter leave by employee | Logged in as Admin | Filter by employee name | Only that employee's leave shown | As expected | Pass |
| TC_LVE_013 | Apply leave with comment | Logged in | Add comment in reason field | Comment saved and visible | As expected | Pass |
| TC_LVE_014 | Leave on public holiday | Logged in | Apply on a configured holiday | Warning shown | Warning not shown | Fail |
| TC_LVE_015 | View leave calendar | Logged in | Go to Leave > Leave Calendar | Calendar with leaves shown | As expected | Pass |
| TC_LVE_016 | Add leave entitlement | Admin | Go to Entitlements > Add | Entitlement added | As expected | Pass |
| TC_LVE_017 | Delete leave entitlement | Admin | Select entitlement > Delete | Entitlement removed | As expected | Pass |
| TC_LVE_018 | Leave type configuration | Admin | Add new leave type | New type appears in list | As expected | Pass |
