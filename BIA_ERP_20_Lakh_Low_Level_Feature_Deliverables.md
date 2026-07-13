# BIA Basic Integrated ERP

## Low-Level Feature and Deliverables Catalogue

**Related bid:** BIA Basic Integrated ERP — BDT 20,00,000  
**Purpose:** Contract scope confirmation, SRS preparation, delivery tracking and UAT acceptance  
**Scope level:** Basic implementation

> Only the deliverables identified below are included in the fixed-price scope. Field names, formulas and print layouts may be clarified in the signed SRS, but clarification cannot add a new workflow, integration, report or module.

---

# 1. Discovery and Solution Design

| ID | Low-level included feature | Deliverable and acceptance output |
|---|---|---|
| DIS-01 | Stakeholder and module-owner identification | Approved stakeholder and responsibility list |
| DIS-02 | Existing-process review | Basic as-is process notes for included modules |
| DIS-03 | Basic future workflows | Approved to-be workflow notes/diagrams |
| DIS-04 | Field and master-data identification | Reviewed basic data dictionary |
| DIS-05 | Payroll, PF and gratuity rules | BIA-approved formulas with worked examples |
| DIS-06 | Basic accounting rules | Approved voucher, account and statement mapping |
| DIS-07 | Report confirmation | Numbered catalogue of up to 25 reports |
| DIS-08 | Integration inventory | Device, SMS, email and gateway information sheet |
| DIS-09 | Scope baseline | Signed basic SRS and feature traceability matrix |
| DIS-10 | Acceptance plan | Approved UAT cases, owners and milestone schedule |

# 2. Platform and Administration

## 2.1 Authentication and User Management

| ID | Low-level included feature | Deliverable and acceptance output |
|---|---|---|
| ADM-01 | Login and logout | Valid user can log in; logout terminates access |
| ADM-02 | Password change | User can change password under configured policy |
| ADM-03 | Administrator password reset | Authorized administrator can reset an account |
| ADM-04 | Failed-login lock | Repeated failed login temporarily locks the account |
| ADM-05 | User activation/deactivation | Deactivated user cannot log in |
| ADM-06 | Basic user profile | Name, employee link, email, phone and status |
| ADM-07 | Predefined roles | Admin, HR, Approver, Payroll, Accounts, Store, Member, File Officer and Employee |
| ADM-08 | Role assignment | Authorized administrator can assign approved roles |
| ADM-09 | Module permissions | Unauthorized modules are hidden and blocked |
| ADM-10 | Basic action permissions | View, create, edit and approve/post where applicable |
| ADM-11 | Employee own-data control | Employee can access only own leave, attendance and payslip |

## 2.2 Organization and Common Setup

| ID | Low-level included feature | Deliverable and acceptance output |
|---|---|---|
| ADM-12 | Organization profile | BIA name, address, logo and contact on agreed outputs |
| ADM-13 | Department master | Add, edit, activate and list departments |
| ADM-14 | Designation master | Add, edit, activate and list designations |
| ADM-15 | Employee-category master | Basic category setup usable in HR/payroll |
| ADM-16 | Holiday calendar | Holiday date/type used by basic attendance calculation |
| ADM-17 | Financial year | One active financial year and basic period list |
| ADM-18 | System settings | Date, currency, organization and numbering settings |
| ADM-19 | Important activity history | Actor, action, time and record reference for sensitive actions |
| ADM-20 | File validation | Agreed file-type and maximum-size checks |
| ADM-21 | Error logging | Traceable server-side application-error log |
| ADM-22 | Basic backup | Scheduled database backup and one restore verification |

# 3. HRM and Employee Profile

| ID | Low-level included feature | Deliverable and acceptance output |
|---|---|---|
| HRM-01 | Employee identity | Unique code, name, gender, birth date and blood group |
| HRM-02 | Contact details | Mobile, email and alternative contact |
| HRM-03 | Addresses | Present and permanent address sections |
| HRM-04 | Family information | Marital status, spouse and multiple children/dependants |
| HRM-05 | Nominee | Name, relationship, contact and basic share information |
| HRM-06 | Emergency contact | Name, relationship, phone and address |
| HRM-07 | Identification | Agreed NID, passport and TIN fields |
| HRM-08 | Photograph | Upload and display employee photograph |
| HRM-09 | Employment details | Joining date, department, designation, category and status |
| HRM-10 | Reporting manager | One direct manager used for basic leave approval |
| HRM-11 | Bank information | Bank, branch, account name and account number |
| HRM-12 | Employment status | Active, inactive, separated and retired status |
| HRM-13 | Transfer history | Effective date, old/new placement and note |
| HRM-14 | Increment history | Effective date, old/new salary reference and note |
| HRM-15 | Separation record | Date, type, note and employee-status update |
| HRM-16 | Employee documents | Type, title, date, upload and authorized download |
| HRM-17 | Employee list/search | Code, name, department, designation and status filters |
| HRM-18 | Employee profile view | Consolidated view of all included HR sections |
| HRM-19 | Excel import | Agreed employee template with basic validation |
| HRM-20 | Excel/CSV export | Export agreed fields from filtered employee list |

# 4. Employee Self-Service

| ID | Low-level included feature | Deliverable and acceptance output |
|---|---|---|
| ESS-01 | Employee dashboard | Links/summary for own profile, leave, attendance and payslip |
| ESS-02 | Own-profile view | Read-only view of approved personal/employment fields |
| ESS-03 | Leave application | Create and submit own leave request |
| ESS-04 | Leave status/balance | View own application history and balance |
| ESS-05 | Attendance view | View own daily/monthly attendance |
| ESS-06 | Payslip access | View/download own released payslip |
| ESS-07 | Notification inbox | View and mark selected in-app messages as read |

# 5. Leave Management

| ID | Low-level included feature | Deliverable and acceptance output |
|---|---|---|
| LEV-01 | Leave-type master | Code, name, active status and basic settings |
| LEV-02 | Annual quota | Agreed quota by basic employee category |
| LEV-03 | Opening balance import | Approved template and reconciled opening balances |
| LEV-04 | Balance ledger | Opening, used and authorized-adjustment entries |
| LEV-05 | Manual adjustment | Authorized increase/decrease with reason and history |
| LEV-06 | Full-day application | Type, dates, reason, contact and working-day count |
| LEV-07 | Half-day application | First-half/second-half request and agreed deduction |
| LEV-08 | Supporting attachment | Optional approved file upload for a request |
| LEV-09 | Balance validation | Prevent request above balance under agreed rule |
| LEV-10 | Date-overlap validation | Prevent overlapping active applications |
| LEV-11 | One-step decision | Assigned approver approves/rejects with optional note |
| LEV-12 | Basic cancellation | Request/approve cancellation under agreed simple rule |
| LEV-13 | Action history | Submission, decision and cancellation timeline |
| LEV-14 | Email notifications | Submission and decision emails through client SMTP |
| LEV-15 | Leave register | Date, type, department and status filters |
| LEV-16 | Balance report | Employee/type opening, used and remaining balance |

# 6. Attendance, Device and Overtime

| ID | Low-level included feature | Deliverable and acceptance output |
|---|---|---|
| ATT-01 | One device profile | One model/site connection information and status |
| ATT-02 | Feasibility test | Documented connectivity/API/SDK test result |
| ATT-03 | Device-employee mapping | Device user ID linked to ERP employee |
| ATT-04 | Automated log collection | Scheduled pull/push when supported by documented device |
| ATT-05 | Excel/CSV fallback | Agreed manual attendance-import template |
| ATT-06 | Raw log register | Source, device ID, employee, punch time and import time |
| ATT-07 | Duplicate handling | Identical punch is not imported twice |
| ATT-08 | Unmapped-log queue | List of device users awaiting employee mapping |
| ATT-09 | Basic office time | Start, end and late-grace configuration |
| ATT-10 | First-in/last-out | First punch as in and last punch as out |
| ATT-11 | Daily status | Present, absent, leave and holiday result |
| ATT-12 | Late and early exit | Flag and minutes calculated by agreed office time |
| ATT-13 | Worked hours | Accepted in/out time difference |
| ATT-14 | Missing punch | Flag incomplete required punch information |
| ATT-15 | Basic overtime | One client-approved overtime rule |
| ATT-16 | Reprocessing | Authorized daily rerun after mapping/correction |
| ATT-17 | Manual correction | Correct in/out/status with mandatory reason/history |
| ATT-18 | Daily attendance report | Employee-wise daily status and punches |
| ATT-19 | Monthly summary | Present, absent, leave, late, hours and overtime |
| ATT-20 | Exception reports | Missing-punch and late-attendance lists |

# 7. Payroll, PF, Gratuity and Salary Advance

## 7.1 Setup and Calculation

| ID | Low-level included feature | Deliverable and acceptance output |
|---|---|---|
| PAY-01 | Monthly payroll period | Open, processing, approved and locked statuses |
| PAY-02 | Basic salary scale | Grade/scale reference assignable to employee |
| PAY-03 | Earning components | Fixed/percentage definitions within agreed limit |
| PAY-04 | Deduction components | Fixed/percentage definitions within agreed limit |
| PAY-05 | Component cap | Maximum 10 active earning/deduction components in total |
| PAY-06 | Employee salary assignment | Effective salary and applicable components |
| PAY-07 | Payroll population | Active employees in one payroll group |
| PAY-08 | Monthly variable input | Agreed bonus, overtime or adjustment input |
| PAY-09 | Attendance input | Approved absence, late and overtime summary |
| PAY-10 | Attendance deduction | One approved absence/late formula |
| PAY-11 | Overtime payment | One approved overtime-payment formula |
| PAY-12 | Basic PF | Employee/employer contribution using one formula |
| PAY-13 | Basic gratuity | Informational/basic value using one formula |
| PAY-14 | Salary advance | Amount, date, installment, deduction and balance |
| PAY-15 | Gross salary | Sum of applicable earnings |
| PAY-16 | Total deduction | Sum of applicable deductions |
| PAY-17 | Net salary | Gross less deductions |
| PAY-18 | Rounding | One approved rounding rule |

## 7.2 Workflow and Output

| ID | Low-level included feature | Deliverable and acceptance output |
|---|---|---|
| PAY-19 | Payroll preview | Employee-wise pre-approval calculation |
| PAY-20 | Exception list | Missing salary/bank and abnormal-result warnings |
| PAY-21 | One-step approval | Authorized payroll approval |
| PAY-22 | Payroll lock | Prevent normal edits after final approval |
| PAY-23 | Payroll register | Earnings, deductions and net salary by employee |
| PAY-24 | Department summary | Department-level payroll totals |
| PAY-25 | PDF payslip | Approved basic earnings/deductions layout |
| PAY-26 | Portal release | Employee access to own released payslip |
| PAY-27 | Payslip email | Optional email through client SMTP |
| PAY-28 | Bank salary sheet | One approved Excel layout |
| PAY-29 | Cash salary sheet | Cash-paid employee output |
| PAY-30 | Cheque salary sheet | Cheque-paid employee output |
| PAY-31 | Payroll journal | One summarized balanced journal for Accounts |

# 8. Basic Accounts and Finance

| ID | Low-level included feature | Deliverable and acceptance output |
|---|---|---|
| ACC-01 | Account types | Asset, liability, income, expense and equity |
| ACC-02 | Basic chart of accounts | Parent/child code, name, type and active status |
| ACC-03 | Opening balance | Debit/credit import with balanced control total |
| ACC-04 | Cash/bank account marking | Identify accounts used in basic registers |
| ACC-05 | Fund master | Code, name and active status |
| ACC-06 | Receipt voucher | Balanced lines, payer/reference, narration and attachment |
| ACC-07 | Payment voucher | Balanced lines, payee/reference, narration and attachment |
| ACC-08 | Journal voucher | Debit/credit lines; reject unbalanced entry |
| ACC-09 | Printable money receipt | Payer, amount, method and reference |
| ACC-10 | Voucher numbering | Automatic sequence by type/year |
| ACC-11 | Draft voucher | Save without ledger impact |
| ACC-12 | One-step posting | Authorized posting updates ledger |
| ACC-13 | Posted protection | Posted voucher cannot be normally edited/deleted |
| ACC-14 | Basic reversal | Reversing journal/reference while retaining original |
| ACC-15 | Voucher attachment | Upload/download approved supporting document |
| ACC-16 | Cash register | Posted cash receipts/payments |
| ACC-17 | Bank register | Posted basic bank receipts/payments |
| ACC-18 | Petty-cash register | Basic payments and running balance |
| ACC-19 | Fund transaction report | Transactions and total by fund |
| ACC-20 | Voucher register | Date, type, number and status filters |
| ACC-21 | General ledger | Opening, debit, credit and closing by account |
| ACC-22 | Trial balance | Debit/credit balances with equal control totals |
| ACC-23 | Income/expenditure | Basic statement from approved account mapping |
| ACC-24 | Basic balance sheet | Asset/liability/equity statement from mapping |
| ACC-25 | Payroll posting | Traceable summarized payroll journal |

# 9. Inventory and Stores

| ID | Low-level included feature | Deliverable and acceptance output |
|---|---|---|
| INV-01 | Item category | Code, name and active status |
| INV-02 | Unit of measure | Basic selectable unit list |
| INV-03 | Item master | Code/SKU, name, category, unit and minimum level |
| INV-04 | Store master | Basic store code/name under one policy |
| INV-05 | Opening stock | Item/store/quantity import and reconciliation |
| INV-06 | Requisition | Requester, item, quantity, purpose and date |
| INV-07 | One-step approval | Approve/reject requisition with note |
| INV-08 | Goods receipt | Store, item, quantity, date and reference |
| INV-09 | Stock issue | Approved/direct reference and issued quantity |
| INV-10 | Employee assignment | Item custody linked to employee |
| INV-11 | Department assignment | Item custody linked to department |
| INV-12 | Product return | Return custody item to store |
| INV-13 | Stock adjustment | Authorized increase/decrease with reason |
| INV-14 | Negative-stock prevention | Block issue above available quantity |
| INV-15 | Item list | Item/category/status filters |
| INV-16 | Stock ledger | Opening, receipts, issues, returns and adjustments |
| INV-17 | Current stock | Available quantity by item/store |
| INV-18 | Requisition report | Pending, approved, rejected and issued status |
| INV-19 | Assignment report | Employee/department custody list |

# 10. Member Management, Billing and Portal

## 10.1 Member and Billing

| ID | Low-level included feature | Deliverable and acceptance output |
|---|---|---|
| MEM-01 | Member category | Code, name and active status |
| MEM-02 | Member creation | Unique number and basic organization/member name |
| MEM-03 | Contact information | Address, email, phone and contact person |
| MEM-04 | Member status | Active, inactive and suspended |
| MEM-05 | Member document | Type, title, upload and authorized download |
| MEM-06 | Member list/search | Number, name, category and status filters |
| MEM-07 | Excel import | Agreed member template and validation |
| MEM-08 | Fee/charge master | Name, amount and active status |
| MEM-09 | Opening due | Basic opening outstanding balance |
| MEM-10 | Invoice | Number, date, member, charge and amount |
| MEM-11 | Printable invoice | Approved basic PDF/print layout |
| MEM-12 | Payment entry | Date, amount, method and reference |
| MEM-13 | Payment allocation | Allocate payment to invoice(s) |
| MEM-14 | Printable receipt | Member, amount, method and invoice reference |
| MEM-15 | Outstanding balance | Invoice amount less allocated payment |

## 10.2 Payment Gateway and Portal

| ID | Low-level included feature | Deliverable and acceptance output |
|---|---|---|
| MEM-16 | One gateway setup | One documented gateway and merchant sandbox |
| MEM-17 | Payment initiation | Start payment for selected invoice |
| MEM-18 | Callback/webhook | Validate provider response and prevent duplicate posting |
| MEM-19 | Failed/cancelled status | Store provider result when available |
| MEM-20 | Member login | Portal user linked to one member |
| MEM-21 | Profile view | Read-only own basic profile/contact |
| MEM-22 | Invoice list | Own invoice/outstanding history |
| MEM-23 | Payment history | Own recorded payments |
| MEM-24 | Document download | Own invoice and receipt PDF/download |
| MEM-25 | Member register | Category/status-filtered member list |
| MEM-26 | Invoice register | Date/member/status invoice list |
| MEM-27 | Collection report | Date/member/method payment list |
| MEM-28 | Outstanding report | Member/invoice outstanding balances |
| MEM-29 | Selected notice | Agreed invoice/payment email or SMS event |

# 11. BIA File and Document Register

| ID | Low-level included feature | Deliverable and acceptance output |
|---|---|---|
| FIL-01 | Authority categories | IDRA, Ministry, SBC, NBR, ICC and FBCCI |
| FIL-02 | File registration | Unique number, subject, authority and opening date |
| FIL-03 | Reference information | External reference, sender/recipient and date |
| FIL-04 | Responsible officer | Current responsible user/employee |
| FIL-05 | Confidentiality flag | Normal/restricted basic access indicator |
| FIL-06 | File status | Open, pending and closed |
| FIL-07 | Inward correspondence | Date, reference, sender, subject and linked file |
| FIL-08 | Outward correspondence | Date, reference, recipient, subject and linked file |
| FIL-09 | Document upload | Title, date, type and attachment |
| FIL-10 | File movement | From, to, movement date and note |
| FIL-11 | Movement history | Retain chronological movement list |
| FIL-12 | Pending-with | Current officer and pending status |
| FIL-13 | Due date | Action/response due date |
| FIL-14 | Basic reminder | In-app/email reminder for agreed due event |
| FIL-15 | File closure | Closure date and note |
| FIL-16 | File search | Number, subject, authority, status and date |
| FIL-17 | File register | Authority/date/status-filtered list |
| FIL-18 | Pending/overdue report | Current officer and due/overdue items |

# 12. Notifications and Communication

| ID | Low-level included feature | Deliverable and acceptance output |
|---|---|---|
| NOT-01 | Email setup | One client-provided SMTP/API and test email |
| NOT-02 | SMS setup | One documented client-provided API and test request |
| NOT-03 | Basic templates | Subject/body with agreed placeholders |
| NOT-04 | Leave events | Submission and decision notifications |
| NOT-05 | Payslip event | Released-payslip notification |
| NOT-06 | Member event | Selected invoice/payment notification |
| NOT-07 | File event | Selected due-date reminder |
| NOT-08 | Send queue | Pending, sent and failed statuses |
| NOT-09 | Basic retry | Administrator retries a failed notification |
| NOT-10 | In-app inbox | Recipient, title, date and read/unread state |

Provider fees, sender-ID approval and provider-side delivery guarantees are excluded.

# 13. Dashboards, Reports and Exports

| ID | Low-level included feature | Deliverable and acceptance output |
|---|---|---|
| RPT-01 | Admin summary | Selected user/module activity counts |
| RPT-02 | HR summary | Active employee and department counts |
| RPT-03 | Attendance summary | Present, absent and late counts |
| RPT-04 | Payroll summary | Gross, deduction and net totals |
| RPT-05 | Accounts summary | Posted receipt and payment totals |
| RPT-06 | Inventory summary | Item, stock and requisition counts |
| RPT-07 | Member summary | Member, invoice, collection and outstanding totals |
| RPT-08 | Report catalogue | Authorized list of agreed reports |
| RPT-09 | Basic filters | Date and agreed module-specific filters |
| RPT-10 | PDF/print | Output where included in signed report catalogue |
| RPT-11 | Excel/CSV | Tabular export where included |
| RPT-12 | Report authorization | Block unauthorized report access |
| RPT-13 | Contractual limit | Maximum 25 signed-off report definitions |

A new print layout, grouping, calculation or statutory format is a separate report definition.

# 14. Data Import and Migration

| ID | Low-level included feature | Deliverable and acceptance output |
|---|---|---|
| MIG-01 | Template package | Employee, leave, account, stock and member templates |
| MIG-02 | Basic validation | Required field, data type and master-reference checks |
| MIG-03 | Error report | Rejected row and reason |
| MIG-04 | One trial import | Trial load in test/UAT environment |
| MIG-05 | Trial reconciliation | Source, accepted and rejected counts |
| MIG-06 | Corrected final files | Client-provided clean approved templates |
| MIG-07 | Final opening-data import | Approved current/opening data in production |
| MIG-08 | Final reconciliation | Signed module-level record/control totals |

Historical transaction conversion, cleansing, duplicate investigation and manual entry are excluded.

# 15. QA, Deployment, Training and Handover

| ID | Low-level included feature | Deliverable and acceptance output |
|---|---|---|
| QAT-01 | Functional testing | Supplier checklist for included critical workflows |
| QAT-02 | Payroll golden cases | Approved expected/actual calculation comparison |
| QAT-03 | Accounting controls | Balanced vouchers, ledger and trial-balance checks |
| QAT-04 | Permission smoke tests | Representative permitted/blocked actions |
| QAT-05 | Integration smoke tests | Available device/email/SMS/gateway cases |
| QAT-06 | UAT release | Accessible UAT version and release notes |
| QAT-07 | UAT issue register | One consolidated defect list and status |
| QAT-08 | Defect correction | Verified in-scope defects pass retest |
| QAT-09 | UAT sign-off | Authorized module/integrated acceptance |
| DEP-01 | Production deployment | Application/database in agreed environment |
| DEP-02 | Domain/SSL support | HTTPS using client-provided domain/certificate |
| DEP-03 | Backup schedule | Verified basic database-backup job |
| DEP-04 | Go-live checklist | Users, data, configuration and contacts confirmed |
| DEP-05 | Administrator training | Completed system-administration session |
| DEP-06 | User training | Role-based train-the-trainer sessions |
| DEP-07 | Basic user guide | Key operating instructions delivered |
| DEP-08 | Technical handover | Source and deployment/database notes after full payment |
| DEP-09 | Defect warranty | 60 calendar days after production acceptance |

# 16. Exclusions and Recommended Upgrade Boundary

| Module | Excluded from BDT 20 lakh basic scope | Recommended later upgrade |
|---|---|---|
| Platform | Custom workflow engine, SSO, advanced SoD and enterprise 2FA | Configurable approvals, data scope, MFA and monitoring |
| HRM | Recruitment, appraisal, training and disciplinary workflow | Complete employee-lifecycle modules |
| Leave | Complex accrual, encashment, delegation and escalation | Advanced policy/approval engine |
| Attendance | Multiple models/sites, roster and rotating/cross-midnight shifts | Multi-site shift/attendance engine |
| Payroll | Automated tax, PF interest/settlement, gratuity provision, arrears and multiple groups | Statutory enterprise payroll |
| Accounts | Advanced AP/AR, budget, bank reconciliation, tax, assets and closing | Full finance/compliance controls |
| Inventory | Procurement/tender/PO, costing, serial, batch, expiry and barcode | Procurement, warehouse and assets |
| Membership | Complex recurring rules, penalty, waiver, refund and multiple representatives | Full lifecycle and portal services |
| Files | Versioning, OCR, watermark, retention, legal hold and complex routing | Enterprise document management |
| Reports | Builder, scheduled reports, deep drill-down and analytics | Expanded reporting and BI |
| Infrastructure | HA, DR site, 24×7 support and independent security assessment | Resilient production architecture |

# 17. Scope-Control Rules

1. Every included item must retain its ID in the signed SRS and UAT checklist.
2. Clarification cannot add a new workflow, formula, integration, role, report or module.
3. The combined report limit is 25 definitions, each with an approved name and column/layout sample.
4. BIA must approve worked examples for attendance, payroll, PF, gratuity and accounting calculations.
5. Device, SMS, email and payment work depends on documented provider facilities and client access.
6. When an external interface is unavailable or incompatible, the documented manual import/entry fallback satisfies the basic delivery unless a change is approved.
7. Any feature without an ID in this catalogue is excluded until added through written change control.
8. Recommended upgrades will be estimated and contracted separately.

---

## Catalogue Approval

| For Bangladesh Insurance Association (BIA) | For the Service Provider |
|---|---|
| Name: | Name: |
| Designation: | Designation: |
| Signature: | Signature: |
| Date: | Date: |

---

*End of low-level feature and deliverables catalogue.*
