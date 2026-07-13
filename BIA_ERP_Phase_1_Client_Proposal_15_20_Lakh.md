# BIA HR, Attendance and Payroll Automation

## Phase 1 Technical and Commercial Proposal

**Prepared for:** Bangladesh Insurance Association (BIA)  
**Proposal date:** 13 July 2026  
**Proposed budget:** BDT 15,00,000–20,00,000  
**Delivery model:** Responsive web application  
**Commercial basis:** Excluding applicable VAT, tax, infrastructure, hardware and third-party service charges

---

# 1. Proposal Overview

This proposal presents a focused first phase of BIA's planned ERP implementation. Phase 1 will automate the highest-priority employee, leave, attendance and payroll activities within the available budget while creating a structured foundation for future modules.

The complete BIA ERP—including full accounting, inventory, membership billing and portal, online payment, and document workflow—is a substantially larger program. Those capabilities are therefore proposed as future phases and are not included in the present fixed-price offer unless specifically identified below.

# 2. Phase 1 Objectives

- Establish a centralized and controlled employee database.
- Replace manual leave applications and approvals with an online process.
- Import and process attendance information for payroll preparation.
- Automate an agreed set of monthly salary calculations.
- Generate salary sheets, payslips and essential management reports.
- Introduce user access control, activity tracking and controlled data backup.
- Prepare a technical foundation that can be extended through separately approved future phases.

# 3. Commercial Options

| Item | Option 1 — Essential | Option 2 — Recommended |
|---|---:|---:|
| **Fixed implementation price** | **BDT 15,00,000** | **BDT 20,00,000** |
| Estimated delivery period | 14–18 weeks | 16–20 weeks |
| Employee and organization setup | Included | Included |
| Leave management | Basic | Enhanced |
| Attendance | Excel/CSV import | Excel/CSV plus one documented device integration |
| Payroll | Basic agreed formulas | Expanded agreed formulas and controls |
| Accounts | Not included | Basic receipt/payment register only |
| Standard reports | Up to 8 | Up to 12 |
| Trial data import | One | One trial plus final import |
| Defect warranty | 45 days | 60 days |

**Recommended option:** Option 2 provides a more usable operational foundation and reduces manual attendance, payroll and reporting work. Direct attendance-device integration is conditional on the device having a stable, documented API/SDK and the client providing access, credentials and vendor cooperation.

# 4. Functional Scope

## 4.1 Organization and Employee Management

Both options include:

- One BIA organization and one operational office/location.
- Department, designation and basic employee-category setup.
- Employee ID and employment status.
- Employee personal and contact information.
- Present and permanent address.
- Joining date, department, designation and reporting manager.
- Basic bank-account information for payroll.
- Photograph and selected document upload.
- Employee list, search, view and export.
- Employee opening-data import using the agreed Excel template.

## 4.2 User Access and Administration

Both options include:

- Secure user login and password management.
- Predefined Administrator, HR, Approver, Payroll and Employee roles.
- Basic module and action permissions.
- Login and important activity history.
- Configuration of holidays and general system settings.
- Employee self-service access to own leave information and payslips.

Advanced configurable roles, branch-level data scope, two-factor authentication and enterprise segregation-of-duties controls are future-phase items.

## 4.3 Leave Management

Option 1 includes:

- Agreed leave types and annual quotas.
- Online leave application.
- One-step approve/reject process.
- Leave balance and basic leave history.
- Basic leave register and balance report.

Option 2 additionally includes:

- Up to two approval steps.
- Employee-category-based leave allocation.
- Basic carry-forward configuration.
- Half-day leave.
- Supporting-document attachment.
- Leave cancellation request.
- Email notification through one client-provided SMTP service.

Complex accrual, encashment, hourly leave, delegation, escalation and rule-based leave policies are not included.

## 4.4 Attendance Management

Option 1 includes:

- Attendance import from an agreed Excel/CSV format.
- Daily clock-in and clock-out summary.
- Present, absent, leave and late status.
- Basic missing-punch identification.
- Monthly attendance summary.
- Authorized manual correction with activity history.

Option 2 additionally includes:

- Integration with one attendance-device model at one site, subject to technical feasibility.
- Device-to-employee mapping.
- Scheduled attendance-log synchronization where supported by the device.
- Duplicate-log handling.
- Basic device synchronization status and error log.
- Agreed late, early-exit and overtime calculation rules.

Multiple devices/sites, rotating rosters, cross-midnight shifts, flexible shifts and undocumented device-protocol reverse engineering are not included.

## 4.5 Payroll Management

Both options include:

- Monthly payroll for one employee group.
- Basic salary and agreed fixed earning components.
- Agreed fixed deduction components.
- Attendance-based deduction using one approved calculation method.
- Salary advance deduction through manual monthly input.
- Payroll preview and processing.
- Payroll approval by one authorized role.
- Payroll-period lock after approval.
- Salary sheet and individual PDF payslip.
- Employee payslip download.

Option 2 additionally includes:

- Up to 10 configured earning and deduction components in total.
- Basic overtime calculation from approved attendance.
- Basic festival bonus processing.
- Joining or separation proration using one agreed formula.
- Payroll variance/exception report.
- Department-wise payroll summary.
- One bank salary sheet in an agreed Excel format.
- Automatic payslip email through a client-provided email service.

Automated income tax, PF interest and settlement, complex gratuity provisioning, multiple payroll groups, retroactive payroll and bank API integration are not included.

## 4.6 Basic Receipt and Payment Register — Option 2 Only

Option 2 includes a simple operational register containing:

- Income and expense heads.
- Money-receipt entry and printable receipt.
- Payment entry.
- Basic cash receipt/payment summary.
- Date-wise and head-wise transaction report.

This is not a double-entry accounting system. It does not include a complete chart of accounts, journal and contra vouchers, general ledger, trial balance, balance sheet, bank reconciliation, budgeting, accounts payable/receivable, VAT or withholding automation.

# 5. Included Reports

The exact layouts will be agreed during requirements confirmation.

Option 1 includes up to eight reports selected from:

1. Employee list.
2. Employee detail.
3. Leave application register.
4. Leave balance report.
5. Daily attendance report.
6. Monthly attendance summary.
7. Payroll register/salary sheet.
8. Employee payslip.

Option 2 includes the above reports plus up to four additional reports selected from:

1. Late and missing-punch report.
2. Department-wise payroll summary.
3. Payroll variance/exception report.
4. Bank salary sheet.
5. Receipt register.
6. Payment register.
7. Cash receipt/payment summary.

Reports beyond the agreed limit or major layout changes after approval will be handled through change control.

# 6. Technical Delivery

- Responsive browser-based application for desktop, tablet and common mobile screen sizes.
- ASP.NET Core backend and relational database.
- Controlled development, testing and production deployment process.
- Database backup configuration for the agreed hosting environment.
- Basic error logging and application-health monitoring.
- Source code and technical handover after full payment.
- Administrator and selected-user training.
- Basic user guide and deployment notes.

The client will provide or fund the server/cloud environment, domain, SSL certificate, email service and attendance-device infrastructure.

# 7. Implementation Plan

| Stage | Option 1 | Option 2 | Deliverables |
|---|---:|---:|---|
| Requirements confirmation and design | 2 weeks | 2–3 weeks | Approved scope, workflows, fields, formulas and report samples |
| Platform and employee management | 3–4 weeks | 3–4 weeks | Login, roles, settings and employee records |
| Leave and attendance | 3–4 weeks | 4–5 weeks | Leave workflow, attendance import/integration and reports |
| Payroll and reports | 4–5 weeks | 4–5 weeks | Payroll calculation, payslips and agreed reports |
| UAT, migration and training | 2–3 weeks | 2–3 weeks | Data import, client testing, fixes and training |
| Deployment and go-live | 1 week | 1 week | Production release and handover |
| **Estimated total** | **14–18 weeks** | **16–20 weeks** | Subject to timely client inputs and approvals |

# 8. Client Responsibilities

BIA will:

- Nominate one authorized project coordinator and relevant subject-matter representatives.
- Confirm requirements, workflows, salary formulas and report layouts in writing.
- Provide clean employee, leave, attendance and payroll data using agreed templates.
- Verify all salary calculations through approved test cases before production use.
- Provide attendance devices, network access, vendor contacts and API/SDK documentation where integration is selected.
- Provide the hosting environment, domain, SSL, email credentials and required infrastructure access.
- Arrange users for timely UAT and provide one consolidated issue list per review cycle.
- Pay third-party, hardware, cloud, SMS, email and device-vendor charges directly.

Delays in decisions, data, access, infrastructure or acceptance will result in a corresponding schedule adjustment.

# 9. Exclusions

The following are outside both Phase 1 options unless added through a written quotation:

- Full double-entry accounting and statutory financial statements.
- Inventory, stores, procurement and fixed-asset management.
- Member management, member billing, online payment and member portal.
- BIA file, correspondence and document workflow management.
- Native Android/iOS applications and offline operation.
- Full Bangla/English bilingual user interface.
- Automated statutory tax, VAT and withholding calculation or returns.
- Advanced PF, gratuity, loan and final-settlement workflows.
- Multiple organizations, substantially different branch policies or multi-tenant operation.
- Multiple attendance-device brands/sites or undocumented protocol development.
- SMS gateway, payment gateway, bank API and third-party system integration.
- Historical-data cleansing, scanning, OCR and manual data entry.
- High availability, separate disaster-recovery environment and 24×7 support.
- Independent penetration testing or formal compliance certification.
- Requirements outside the approved Phase 1 scope document.

# 10. Payment Schedule

## Option 1 — BDT 15,00,000

| Milestone | Percentage | Payment |
|---|---:|---:|
| Contract signing and mobilization | 30% | BDT 4,50,000 |
| Requirements and design approval | 20% | BDT 3,00,000 |
| Employee, leave and attendance release | 25% | BDT 3,75,000 |
| Payroll completion and UAT release | 15% | BDT 2,25,000 |
| Production go-live and handover | 10% | BDT 1,50,000 |
| **Total** | **100%** | **BDT 15,00,000** |

## Option 2 — BDT 20,00,000

| Milestone | Percentage | Payment |
|---|---:|---:|
| Contract signing and mobilization | 30% | BDT 6,00,000 |
| Requirements and design approval | 20% | BDT 4,00,000 |
| Employee, leave and attendance release | 25% | BDT 5,00,000 |
| Payroll, basic registers and UAT release | 15% | BDT 3,00,000 |
| Production go-live and handover | 10% | BDT 2,00,000 |
| **Total** | **100%** | **BDT 20,00,000** |

Invoices are payable within 10 calendar days. Applicable VAT and taxes will be handled according to Bangladesh law and the legal/tax status of the parties. BIA will provide all legally required withholding certificates.

# 11. Acceptance and Change Control

- Detailed fields, formulas, workflows and report layouts will be documented and approved before development of the relevant feature.
- BIA will accept a milestone or provide one consolidated written list of material defects within seven business days of delivery.
- A defect means an approved requirement that does not operate as documented. New requirements, policy changes and new report formats are changes, not defects.
- Work outside the signed scope requires written impact analysis, approval, additional price and, where applicable, schedule adjustment.
- Device integration will proceed only after a technical feasibility check. If the device cannot be integrated because of unavailable or incompatible vendor facilities, attendance Excel/CSV import will be delivered and any unused integration effort will be reassigned only by mutual written agreement.

# 12. Warranty and Support

- Option 1 includes a 45-calendar-day defect warranty after production acceptance.
- Option 2 includes a 60-calendar-day defect warranty after production acceptance.
- Warranty covers correction of reproducible defects in the approved scope.
- User mistakes, source-data problems, infrastructure failures, device/vendor failures, statutory changes and new requirements are outside the defect warranty.
- Ongoing maintenance, support and enhancements may be contracted separately after the warranty period.

# 13. Future ERP Phases

Subject to separate approval and budget, the Phase 1 foundation may later be expanded through:

- Phase 2: Full Accounts and Finance.
- Phase 3: Inventory, Stores and Procurement.
- Phase 4: Member Management, Billing, Payment and Portal.
- Phase 5: File and Document Workflow Management.
- Phase 6: Advanced integrations, analytics, security and disaster recovery.

Each future phase will have its own requirements, delivery schedule, commercial offer and acceptance criteria.

# 14. Commercial Validity

- This proposal is valid for 30 calendar days from the proposal date.
- Prices exclude applicable VAT and tax, hosting, hardware and third-party charges.
- The fixed price assumes timely decisions, approved requirements and the limits stated in this document.
- Final implementation will begin after contract signature, advance payment and project mobilization.

# 15. Recommendation

**Option 2 — BDT 20,00,000 is recommended** because it provides a stronger operational solution through attendance-device integration where technically feasible, broader payroll controls, additional reports, a basic receipt/payment register, and a longer warranty.

If the available budget must remain at BDT 15,00,000, Option 1 should be adopted as an essential HR, leave, attendance-import and payroll phase. Neither option should be interpreted as delivery of the complete multi-module BIA ERP.

---

## Proposal Acceptance

| For Bangladesh Insurance Association (BIA) | For the Service Provider |
|---|---|
| Name: | Name: |
| Designation: | Designation: |
| Signature: | Signature: |
| Date: | Date: |

---

*End of proposal.*
