# BIA Accounts, HRM, Payroll, Inventory, Member and File Management ERP

## Professional Software Estimation and Proposal Advisory Report

**Prepared:** 11 July 2026  
**Estimate class:** Rough Order of Magnitude (ROM), proposal-stage, expected accuracy **-20% / +25%**  
**Source reviewed:** *BIA Proposal for Accounts and Payroll Software Development _2037 (1).pdf*, all 3 pages  
**Delivery basis:** Responsive web ERP; one organization; Bangla/English-ready; production-grade controls; no native mobile app unless added  
**Effort convention:** 1 man-day (MD) = 8 productive hours; 20 MD = one person-month  
**Commercial currency:** USD, exclusive of VAT/tax, cloud/SMS/payment/device fees and hardware

> **Critical qualification.** The source document is a high-level feature list, not a signed SRS. It explicitly names six business areas and three technology options but does not define workflows, statutory formulas, approval matrices, accounting rules, data volume, acceptance criteria, integrations or non-functional requirements. This report preserves the stated scope and adds the capabilities normally required to make it operational. Added items must be confirmed during discovery and placed in the signed scope baseline.

---

# 1. Executive Summary

## Overall project

BIA requires a centralized ERP covering employee records, leave, attendance-device integration, payroll, accounting, inventory, membership billing and payment, regulatory/organizational file tracking, notifications, portals and management reporting. The platform will replace fragmented spreadsheets/manual registers with controlled workflows, a single audit trail and near-real-time management information.

## Business objective

- Establish one authoritative source for employee, member, finance, stock and document data.
- Automate leave-to-attendance-to-payroll and member-invoice-to-receipt workflows.
- Improve financial control through chart of accounts, vouchers, approvals, ledgers and reconciliation.
- Provide employee/member self-service, automated email/SMS notices and downloadable documents.
- Strengthen governance through RBAC, segregation of duties, immutable audit logs and backups.

## Expected users

Executive management, HR, payroll, accounts/cash/bank teams, inventory/store officers, membership officers, registry/file officers, department heads, employees, members, internal/external auditors, IT administrators and read-only reviewers. A planning assumption of **50-150 internal users, 500-5,000 members and 50 concurrent sessions** is used; final infrastructure sizing depends on measured volumes.

## End-to-end business workflow

1. Administrators configure organization, departments, employees, members, fiscal periods, payroll rules, leave policies, products, warehouses and approval matrices.
2. Employees use self-service for profile, leave, attendance, payslip and requests; supervisors approve through delegated workflows.
3. Device punches are synchronized, normalized and converted into attendance, lateness, overtime and exceptions; approved results feed payroll.
4. Payroll calculates earnings, deductions, advances, PF, gratuity and net pay; authorized officers approve, lock and generate bank/cash/cheque outputs and payslips.
5. Accounts receives approved payroll, member billing, inventory purchases/issues and cash transactions as controlled vouchers and ledger postings.
6. Inventory manages request, approval, receipt, stock, issue/assignment, return and valuation.
7. Membership manages onboarding, invoices, online payments, receipts, notices, portal access and arrears.
8. File management registers and routes records relating to IDRA, Ministry, Sadharan Bima Corporation, NBR, ICC and FBCCI with metadata, versioning, reminders and retention.
9. Dashboards, reports and audit evidence support management and compliance review.

## Complexity assessment

**Overall: High / enterprise-critical.** Payroll and double-entry accounting are rule-dense; biometric integration is vendor/protocol dependent; payment, SMS, email and backup introduce external dependencies; finance/payroll data is sensitive; and historical migration must reconcile to opening balances. Complexity becomes **very high** if multi-company, government pay scales, tax automation, pension, procurement/tendering, native mobile apps or HA/DR across sites are required.

## Suggested implementation strategy

Use phased delivery with a 4-6 week discovery/SRS stage and contractual scope gate. Build a modular monolith using clean bounded contexts, not distributed microservices initially. Release foundations/HR first; then leave/attendance; payroll; accounts; inventory/member/file management; finally integrations, migration and stabilization. Require parallel payroll for at least two cycles and financial opening-balance sign-off before go-live.

---

# 2. Functional Module Breakdown

The labels **Source** and **Production addition** provide scope traceability.

## 2.1 HRM and Employee Profile

- **Source:** personal, address, marital, children, nominee and emergency-contact information.
- Employee ID, photograph, signature, contact, nationality, NID/passport/TIN and bank details.
- Organization, branch, department, section, designation, grade, employment type and reporting line.
- Joining, confirmation, probation, contract, retirement and service-status lifecycle.
- Qualifications, professional certification, skills, experience and references.
- Dependants, nominees with allocation percentage and emergency contacts.
- Document upload, type, expiry, verification, access control and version history.
- Job/history timeline: promotion, increment, transfer, deputation, disciplinary action and status change.
- Training catalogue, nomination, attendance, cost and result.
- Separation: resignation, termination, retirement, clearance, final settlement and exit interview.
- Employee directory, advanced search, bulk import/export and HR dashboard.
- Self-service change requests with approval rather than uncontrolled master-data edits.

## 2.2 Leave Management

- **Source:** leave types/quotas, online application, email/SMS on application and approval, balance, approve/reject and reporting.
- Policy by grade/type/gender/tenure; accrual, carry-forward, expiry, encashment and negative-balance rules.
- Calendar/working-day computation; weekends and holidays; half-day/hourly and consecutive leave.
- Attachment/medical-certificate rules and substitute/acting employee.
- Configurable multi-level approval, delegation, escalation, cancellation, recall and resubmission.
- Team leave calendar, overlap/blackout checks, opening balances and year-end processing.
- Balance ledger with earned, used, adjusted, lapsed and carried-forward entries.
- Return-from-leave and attendance/payroll integration.

## 2.3 Attendance, Shift and Overtime

- **Source:** punch-machine integration, automated logs, clock-in/out, daily/monthly/yearly reports, summary, late/extra-late, working/present/leave days, required hours and overtime.
- Device registry, employee-device mapping, vendor adapter, polling/webhook, retry and sync health.
- Immutable raw punch storage, deduplication, timezone/location normalization and manual mapping queue.
- Shift/roster, grace period, cross-midnight shift, holiday/weekend and flexible-hours policy.
- First-in/last-out or paired-punch calculation; missing/duplicate punch and anomaly detection.
- Late, early departure, absence, work-from-field/official duty and attendance regularization.
- Overtime request, eligibility, approval, rounding, rate/multiplier and payroll feed.
- Manual attendance correction with maker-checker approval and before/after audit.
- Daily processing/reprocessing, period lock and attendance dashboard.

## 2.4 Payroll, PF, Gratuity and Advances

- **Source:** salary scale, department-wise payroll, payslip, bank/cash/cheque sheets, deduction, advance adjustment, automatic email payslip; PF and gratuity are named under Accounts.
- Pay grade/scale, step, salary structure, effective dating and employee compensation assignment.
- Earnings: basic, house rent, medical, conveyance, allowance, arrears, bonus and overtime.
- Deductions: absence/late, tax, PF, loan/advance, welfare, insurance and configurable deductions.
- Gross-to-net engine with proration, joining/separation mid-period, retroactive adjustment and rounding.
- Payroll calendar, input collection, validation, preview, exception list, approval, lock/unlock and rerun control.
- Advance/loan request, disbursement, installment schedule, balance and payroll recovery.
- Employee/employer PF contribution, interest/allocation, nomination, ledger, settlement and statements.
- Gratuity eligibility, provisioning, calculation and final settlement.
- Bank advice/upload file, cash sheet, cheque register, payslip PDF/email and password protection.
- Payroll journal posting to Accounts, cost-center allocation and reconciliation.
- Tax rules/declaration/certificate only after BIA confirms statutory scope and formula ownership.

## 2.5 Accounts and Finance

- **Source:** expense head/sub-head, income head, account types/info, money receipt, payment, fund, summary, petty cash, PF, gratuity, BIA Foundation and reports.
- Organization/foundation books, fiscal year/period, chart of accounts and account hierarchy.
- Cost centers, departments, projects/funds, bank/cash books and opening balances.
- Receipt, payment, journal and contra vouchers with numbering, attachments and narrations.
- Voucher workflow: draft, submit, check, approve, post, reverse; maker-checker and period lock.
- General ledger, subsidiary ledger, trial balance, income/expenditure, balance sheet and cash flow.
- Accounts receivable: member/customer invoice, debit/credit note, allocation, aging and collection.
- Accounts payable: supplier, bill, payment, advance and aging (production addition; procurement depth TBD).
- Bank account, cheque book, deposit, transfer and bank reconciliation.
- Petty-cash float, replenishment, expense claim, limits and reconciliation.
- Budget by account/cost center/fund, revision, commitment and budget-vs-actual.
- Fixed assets and depreciation are recommended but separately confirmable if BIA only expects inventory.
- Withholding tax/VAT fields, certificates and statutory returns subject to Bangladesh rules validation.
- Year-end close, opening transfer, audit schedules, financial notes and configurable approval limits.

## 2.6 Inventory and Stores

- **Source:** add/list/search product, requisition, received confirmation, product assignment/details and payment received detail/report.
- Item category, unit of measure, SKU/barcode, brand/model, reorder level and active status.
- Warehouse/store/bin and department/custodian master.
- Requisition, supervisor/store approval, partial issue, rejection and fulfillment.
- Goods receipt with supplier/reference, inspection, quantity, cost and attachment.
- Stock issue, assignment to employee/department/member, acknowledgement and custody history.
- Return, transfer, adjustment, damage/loss, disposal and stock count/reconciliation.
- Batch/serial/warranty/expiry tracking where applicable.
- Stock ledger, valuation method, available/reserved stock and reorder alert.
- Supplier and purchase order are necessary if BIA expects purchase-to-stock; otherwise integrate with an external procurement process.
- Inventory financial posting and payment reporting require Accounts linkage; inventory does not itself receive unrelated payments.

## 2.7 Member Management and Portal

- **Source:** add/list members, bill invoice, online bill payment, portal, SMS notices and reports.
- Member category/type, organization/contact, registration number, status and lifecycle.
- Application, supporting documents, verification, approval, membership number and certificate/card.
- Contact persons, branches, nominees/representatives and communication preferences.
- Fee/charge schedule, recurring billing, prorating, invoice, adjustment, waiver and credit note.
- Opening dues, collection allocation, arrears, aging, suspension/renewal and reinstatement.
- Online payment initiation, callback/webhook validation, reconciliation, refund and digital receipt.
- Portal: profile, invoices, payment history, online payment, receipts, notices, documents and support requests.
- Bulk notice, audience segmentation, delivery status and consent/opt-out where legally required.
- Member dashboard, directory controls, import/export and membership analytics.

## 2.8 BIA File and Document Management

- **Source:** IDRA, Ministry, Sadharan Bima Corporation, NBR, ICC and FBCCI information.
- File/register number, subject, authority/category, sender/recipient, dates, owner and confidentiality.
- Inward/outward correspondence, reference number, linked member/employee/vendor and physical location.
- Document upload, metadata, tags, OCR-ready indexing, version, check-in/check-out and preview.
- File movement/routing, notes, actions, acknowledgement, pending-with and movement history.
- Due date, reminder, escalation, response tracking and closure.
- Full-text/metadata search, saved filters, access classification and download watermark.
- Retention schedule, archive, legal hold and controlled disposal.
- The six source categories should be configurable authorities, not six hard-coded applications.

## 2.9 Notifications and Communications

- Email, SMS, in-app and optional push channels; reusable templates and Bangla/English variants.
- Event subscriptions, recipient rules, queued sending, retry, throttle and delivery status.
- Leave, payroll, member bill/payment, approval, file due-date, stock and security notifications.
- User notification center, read/unread, preferences and administrator resend.
- Cost/credit monitoring, provider logs and sensitive-data masking.

## 2.10 Reports, Dashboards and Analytics

- Role-specific KPI dashboards, filters, drill-down and date/department comparisons.
- Tabular reports with pagination, saved filters, PDF/Excel/CSV and scheduled delivery.
- Report authorization, confidential-payroll masking, watermark and generation audit.
- Snapshot/period-based reporting so historical figures do not change silently.

## 2.11 Settings, Security and Administration

- Organization, branch, department, designation, grade, holidays, fiscal year and numbering settings.
- Users, roles, permissions, data scope, approval matrix, delegation and limits.
- Payroll/leave/attendance/account/inventory/member configuration with effective dates.
- Localization, timezone, currency, date/number format and email/SMS/integration settings.
- Feature flags, background-job monitoring, audit search, health dashboard and system announcements.
- Import templates, validation/error report, reference data and controlled maintenance tools.

---

# 3. Missing Features

| Missing or underdefined capability | Why it is necessary | Scope treatment |
|---|---|---|
| Organizational hierarchy and effective-dated master data | Every approval, payroll and report depends on it | Include |
| Employee lifecycle/history/documents | A profile alone cannot run HR operations or audit changes | Include |
| Shift, roster, holiday and attendance correction | Raw punches do not equal payable attendance | Include |
| Payroll formula catalogue and statutory tax | Prevents disputed net-pay calculations | Discovery + change control if complex |
| Payroll approval, lock and parallel run | Prevents unauthorized/repeated payroll and go-live errors | Include |
| Full double-entry accounting | Heads plus receipts/payments do not produce auditable statements | Include core finance |
| Chart of accounts, vouchers, ledgers and closing | Required for trial balance and financial statements | Include |
| Budgeting, AP/AR and reconciliation | Fundamental finance control and liquidity visibility | Include baseline |
| Procurement workflow | Requisition/receipt needs sourcing and PO traceability | Optional pending confirmation |
| Fixed assets | Durable assigned products need capitalization/depreciation | Optional module |
| Member lifecycle, recurring billing, arrears/refunds | Required for reliable dues and portal history | Include |
| Document workflow/version/retention | “Information” categories alone are not file management | Include |
| Configurable approvals/delegation/SLA | Government/association processes require accountable authorization | Include |
| Master-data governance and duplicate detection | Prevents inconsistent employees, members and accounts | Include |
| Data migration and reconciliation | Existing records/opening balances must enter the ERP safely | Include capped cycles |
| Audit trail and segregation of duties | Critical for payroll, accounts and compliance | Include |
| Localization/Bangla and accessibility | Likely operational need; exact standard must be agreed | Confirm |
| Search, bulk import/export and attachments | Essential for real production volume | Include |
| Backup restore tests and DR objectives | A backup is not useful unless recoverable | Include baseline |
| Performance, availability and retention targets | Needed to design/test infrastructure objectively | Confirm in NFR workshop |
| Help, SOP, training and support SLA | Determines adoption and post-launch responsibility | Include defined deliverables |
| Privacy/consent/data retention | HR, nominee, NID and payment data are sensitive | Include policy enforcement |
| API/device/provider ownership | Avoids vendor lock-in and unpriced integration risk | Client dependency |

---

# 4. User Roles

Permissions must be granular actions plus data scope (organization/branch/department/self), never role names hard-coded in business logic.

| Role | Principal permissions |
|---|---|
| Super Admin | Tenant-wide configuration, emergency access; cannot silently erase audit data |
| System Administrator | Users, integrations, jobs, backups and health; no routine payroll posting |
| Security/RBAC Administrator | Roles, permission assignment, access review and session revocation |
| HR Administrator | Employee masters, lifecycle, policy and HR reports |
| HR Officer | Day-to-day employee data and documents within assigned scope |
| Leave Administrator | Leave types, balances, corrections and leave reports |
| Attendance Administrator | Devices, shifts, logs, exceptions and reprocessing |
| Department Head/Line Manager | Team view; approve leave, attendance and requisitions within authority |
| Payroll Officer | Payroll inputs, calculation, draft outputs and exception resolution |
| Payroll Approver | Review/approve/lock payroll; no unauthorized master-data changes |
| Accounts Administrator/Controller | COA, periods, controls, posting policy and financial statements |
| Accounts Officer | Prepare receipts/payments/journals and reconcile assigned books |
| Cashier | Money receipts, cash payment and daily cash closing within limits |
| Bank/Reconciliation Officer | Bank transactions, cheque controls and reconciliation |
| Budget/Fund Officer | Budget/fund setup, allocation, revision and variance review |
| Inventory/Store Officer | Item/store masters, receipt, issue, return, count and stock report |
| Inventory Approver | Approve requisitions, adjustments, disposal and transfers |
| Membership Administrator | Member masters, fee policy, status, portal and reports |
| Membership/Billing Officer | Application, invoice, receipt allocation, notices and follow-up |
| File/Registry Officer | Register, route, version, archive and search authorized files |
| Compliance Officer | Regulatory due dates, evidence, read/review and compliance reporting |
| Employee | Self-profile, leave, attendance, payslip, documents and own requests |
| Member/Member Representative | Own organization profile, invoices, payments, receipts and notices |
| Internal Auditor | Read-only cross-module audit, vouchers, logs and export; no mutation |
| External Auditor | Time-bound, restricted read-only evidence access |
| Executive/Management | Consolidated dashboards, approved reports and drill-down by mandate |
| Data Entry Operator | Create/import drafts only; no approval/posting |
| Report Viewer | Run specifically permitted reports with masking/data scope |
| Support/Help Desk | Tickets and safe diagnostics; impersonation only if explicitly controlled |
| API/Integration Service Account | Least-privilege machine access, IP/secret controls and no interactive login |

---

# 5. Database Design

## Estimated table count

| Bounded context | Estimated tables | Examples |
|---|---:|---|
| Identity, RBAC and security | 18 | users, roles, permissions, role permissions, sessions, MFA, API clients |
| Organization and common masters | 14 | organization, branch, department, designation, grade, calendar, lookup |
| HR employee management | 24 | employee, address, family, nominee, contact, education, history, document |
| Leave | 12 | type, policy, allocation, balance ledger, request, approval, delegation |
| Attendance/shift/device | 18 | device, mapping, raw punch, shift, roster, daily result, exception, overtime |
| Payroll/PF/gratuity/advance | 24 | structure, component, assignment, run, result, earning, deduction, loan, PF |
| Accounts and finance | 30 | COA, fiscal period, voucher/header/detail, ledger, bank, reconciliation, budget |
| Inventory | 18 | item, warehouse, requisition, receipt, issue, transfer, stock ledger, count |
| Membership/billing/payment | 22 | member, contact, fee, invoice, invoice line, payment, allocation, webhook |
| File/document management | 14 | file, authority, correspondence, document, version, movement, retention |
| Notification | 9 | template, event, queue, delivery, preference, provider log |
| Reporting/audit/integration | 12 | audit event, export job, import batch/error, report schedule, outbox/inbox |
| **Estimated physical tables** | **215** | includes junction/history/configuration tables |

**Proposal range:** 190-230 tables. Early logical modelling may show fewer entities; audit, effective dating, many-to-many links, workflow instances and integration reliability create additional physical tables.

## Principal relationships

- Organization → branch → department → employee; employee has many addresses, dependants, documents and job-history entries.
- Employee → leave allocation/balance ledger → leave request → approval steps.
- Employee/device mapping → raw punches → processed daily attendance → overtime/exception → payroll input.
- Employee → compensation assignment → payroll run → result lines → bank output/accounting journal.
- Chart of account → voucher lines; posted lines generate balanced ledger entries by period, cost center and fund.
- Item → warehouse stock ledger; requisition → issue; receipt/issue/adjustment creates immutable stock movements.
- Member → fee schedule/invoice → payment → allocation → money receipt and accounting voucher.
- File → documents/versions/movements; files may reference member, employee or financial record without duplicating the master.
- Audit events reference actor, action, entity key, timestamp, correlation ID and before/after metadata.

Use UUID/ULID or controlled numeric keys consistently, optimistic concurrency, soft deactivation (not blanket soft delete), UTC timestamps, effective dates, row-version fields, unique business constraints and partition/archival strategy for punch/audit/notification tables.

---

# 6. API Estimation

An “API” below means a distinct HTTP operation/endpoint, not merely a controller. Internal MediatR commands are not counted separately.

| API family | Estimated endpoints |
|---|---:|
| Authentication, MFA, session, password | 22 |
| Users, RBAC, organization and settings | 52 |
| HRM and employee lifecycle | 58 |
| Leave | 32 |
| Attendance, shift, device and overtime | 48 |
| Payroll, advance, PF and gratuity | 58 |
| Accounts and finance | 74 |
| Inventory | 44 |
| Member, billing, portal and payment | 50 |
| File/document management | 34 |
| Notifications | 18 |
| Dashboard and analytics | 20 |
| Report generation/download/scheduling | 28 |
| Import/export and migration | 22 |
| Integration webhook/health/admin | 16 |
| **Estimated total** | **576** |

Composition: approximately **360 command/query CRUD/workflow endpoints**, **20 dashboards**, **28 reports**, **22 authentication**, **18 notification**, **22 import/export**, and **106 specialized approval, posting, device, payment and integration operations**. OpenAPI/Swagger, versioning, validation, pagination, idempotency for financial callbacks, rate limiting, problem-details errors and correlation IDs are required.

---

# 7. Screen Estimation

A screen is a distinct route/workspace; modal dialogs and reusable selectors are not separately counted.

| UI area | Estimated screens |
|---|---:|
| Login, MFA, recovery, access denied | 8 |
| Global profile, inbox, search and help | 8 |
| Admin, RBAC, organization and settings | 30 |
| HRM | 30 |
| Leave | 15 |
| Attendance/device/shift | 24 |
| Payroll/PF/gratuity/advance | 27 |
| Accounts/finance | 36 |
| Inventory | 24 |
| Member administration/billing | 27 |
| File/document management | 18 |
| Notification administration | 8 |
| Management dashboards | 12 |
| Report catalogue/viewer/scheduler | 14 |
| Employee self-service portal | 15 |
| Member portal | 12 |
| **Estimated total unique screens** | **308** |

All 308 routes should be responsive at desktop/tablet; approximately **70 high-frequency pages** should receive explicit small-mobile optimization. Native Android/iOS apps, offline operation and biometric capture from a phone are excluded.

---

# 8. Reports

The estimate includes about **65 report definitions and 95 output variants** (PDF/Excel/CSV/chart). Final statutory layouts require client-approved samples.

## HR and leave

- Employee master/detail, directory, headcount, demographics, joining/separation, vacancy, promotion/transfer, contract/probation/retirement due, document expiry and training history.
- Leave balance, leave ledger, application register, department/month/type usage, absent-on-leave, pending approval and year-end liability.

## Attendance

- Daily attendance, punch detail, monthly muster/summary, yearly summary, present/absent, late/extra-late, early exit, missing punch, shift/roster, required vs worked hours, overtime and device-sync exception.

## Payroll/PF/gratuity

- Payroll register, department/cost-center summary, salary sheet, payslip, bank advice/upload, cash sheet, cheque sheet, earnings/deductions, variance, arrear/bonus/overtime, advance balance/installment, PF contribution/ledger/statement and gratuity/provision/final settlement.

## Accounts

- Money receipt, payment/receipt/journal/contra register, day book, cash book, bank book, general/subsidiary ledger, trial balance, income and expenditure, balance sheet, cash flow, budget vs actual, fund statement, cost-center statement, petty cash, AP/AR aging, bank reconciliation, cheque register, withholding/VAT schedules and audit voucher listing.

## Inventory

- Item/store list, stock ledger, current stock, valuation, receipt, issue, requisition status, assignment/custody, return/transfer/adjustment, damage/disposal, stock count variance, reorder, slow/nonmoving and serial/warranty/expiry.

## Membership

- Member register/status/category, new/renewed/suspended, invoice register, collection, payment-method reconciliation, receipt, outstanding/aging, waiver/adjustment, failed payment, SMS delivery and member statement.

## File management, security and analytics

- Authority/category register, inward/outward correspondence, file movement, pending-with, due/overdue response, document version and retention/disposal.
- User access, role-permission matrix, login failure, active session, master-data change, approval turnaround and audit-event export.
- Executive KPI charts: workforce trend, attendance and lateness, payroll trend/variance, income/expense/cash, budget variance, dues/collections, stock value/turnover and overdue files.

---

# 9. Third-Party Integration

| Integration | Complexity | Key considerations / estimate assumption |
|---|---|---|
| Attendance device | High | Vendor SDK/API, LAN reachability, push vs pull, firmware, employee IDs, duplicate/offline data; one documented model included |
| SMS gateway | Medium | API, sender ID, Bangla Unicode segmentation, delivery report, balance, template/consent; one provider |
| Email server | Low-Medium | SMTP/API, SPF/DKIM/DMARC, bounce handling, throttling and attachment security |
| Google Cloud backup | Medium | Encrypted database/object backup, service account, retention, restore test, egress; storage fees excluded |
| Payment gateway | High | Hosted checkout, signed webhook, idempotency, settlement/reconciliation, refund and PCI scope; one gateway/merchant |
| Active Directory/Entra ID | Medium-High | LDAP/OIDC/SAML choice, group mapping, hybrid network, MFA and lifecycle; optional unless confirmed |
| Document storage (MinIO/S3) | Medium | Versioning, malware scan, presigned access, retention, encryption and backup |
| Bank payment file/API | High | Bank-specific format/certificate/approval and test environment; one template included, API optional |
| Accounting/other legacy system | High | Mapping, opening balance, ownership and reconciliation; interface not stated in source |

Integration pricing assumes timely sandbox credentials, current English documentation and one certification cycle. Undocumented device reverse engineering, provider fees, additional banks/gateways/models and private network work are change requests.

---

# 10. Technical Architecture

## Recommended stack

- **Runtime:** ASP.NET Core **10 LTS** and C#; if the tender contract rigidly says ASP.NET Core 9, use 9 only with an agreed upgrade before its support end. As of this report date, Microsoft lists .NET 9 as STS ending 10 November 2026 and .NET 10 LTS through 14 November 2028 ([Microsoft .NET support policy](https://dotnet.microsoft.com/en-us/platform/support/policy)).
- **Architecture:** modular monolith, Clean Architecture boundaries and pragmatic DDD bounded contexts. This provides separation without premature distributed-system cost.
- **Application pattern:** CQRS with MediatR for workflow-rich commands/queries; do not force CQRS/event sourcing onto trivial lookups.
- **Frontend:** React + TypeScript, a mature enterprise component library, TanStack Query and accessible responsive design. MVC/Razor remains acceptable for simpler internal pages, but React better supports the two portals and dense workspaces.
- **Database:** PostgreSQL 17+ preferred for license efficiency and strong relational capability; SQL Server 2022/2025 when BIA already has Microsoft licensing, DBA skills or reporting dependencies.
- **Persistence:** EF Core, explicit transactions, database constraints and optimized SQL/read models where justified.
- **Cache/coordination:** Redis for distributed cache, short-lived reference data and rate limiting—not the system of record.
- **Files:** MinIO on-premises or S3-compatible cloud object storage; metadata remains relational.
- **Jobs:** Hangfire for payroll/report/notification/backup orchestration with controlled retries and dashboards.
- **Real time:** SignalR for in-app notifications and live job status.
- **Identity:** ASP.NET Core Identity, OIDC/OAuth2, short-lived JWT for APIs, secure refresh rotation; optionally federate AD/Entra.
- **API:** REST, OpenAPI/Swagger, versioning, idempotency and outbox pattern for reliable external events.
- **Observability:** Serilog structured logs; OpenTelemetry; Elastic/OpenSearch only if operational budget supports it, otherwise centralized rolling logs plus metrics first.
- **Deployment:** Docker containers behind reverse proxy/WAF; separate application, worker, database, Redis and object-store concerns.
- **CI/CD:** GitHub Actions or Azure DevOps—not both initially—for build, test, security scan, migration packaging and controlled environment promotion.

## Logical deployment

Client/browser → WAF/reverse proxy → React web/API → application modules → PostgreSQL/SQL Server; asynchronous work goes through Hangfire/outbox; Redis accelerates non-authoritative reads; MinIO stores documents; adapters isolate device/SMS/email/payment/bank providers. Separate development, test/UAT and production environments are mandatory.

The source’s “Intel Xeon 8 core, 32 GB RAM, 1 TB SSD” is only a preliminary single-server minimum, not a capacity or HA design. Production sizing requires user, member, document, punch, retention, concurrency, RTO/RPO and growth figures.

---

# 11. Security

| Control area | Required design |
|---|---|
| Authentication | Identity/OIDC, verified accounts, throttling, lockout and secure recovery |
| Authorization | Deny-by-default policy authorization; action + data-scope checks at API and UI |
| RBAC/SoD | Configurable roles; maker cannot approve own financial/payroll transaction; quarterly access review |
| MFA/2FA | Mandatory for privileged, payroll, finance and remote users; TOTP/passkey preferred, SMS fallback |
| Audit trail | Append-only actor/action/time/entity/correlation/device metadata; before/after for sensitive changes; export protection |
| Encryption | TLS 1.2+, HSTS; encrypted disks/backups/object storage; application-level protection for selected NID/bank/secrets |
| Secrets | Vault/environment secret store, rotation, no secrets in source/logs |
| Password policy | 12+ character passphrases, breached-password screening, no routine forced expiry unless policy requires; strong admin controls |
| Session management | Short access token, rotated refresh token, idle/absolute timeout, device/session list and revocation |
| Application security | OWASP ASVS-informed validation, CSRF where cookie-based, XSS/CSP, SQL injection prevention, upload allowlist and malware scan |
| Financial integrity | Balanced posting, idempotency, period lock, reversal not deletion, approval limit and sequence control |
| Backup | Daily encrypted backup, transaction-log/PITR where supported, off-site copy, retention and monthly restore test |
| Disaster recovery | Proposed baseline RPO 4 hours/RTO 8 hours; client must approve; annual DR exercise |
| Monitoring | Security events, privileged action, failed login, integration failure and backup alerts |
| Privacy | Least data, masked displays/exports, retention and disposal, consent/preferences and privileged export logging |
| Assurance | SAST, dependency/container scanning, DAST and independent penetration test before production |

---

# 12. Development Roadmap

| Phase | Duration | Principal outputs / exit gate |
|---|---:|---|
| 0. Mobilization | 1 week | Governance, stakeholders, plan, environments and document register |
| 1. Discovery and process mapping | 4-6 weeks | As-is/to-be, data/integration inventory, report samples, NFRs |
| 2. SRS, UX and architecture | 4-6 weeks overlapping | Signed backlog/SRS, prototype, data model, architecture and acceptance criteria |
| 3. Platform + HR foundation | 6-8 weeks | Identity/RBAC/audit/settings, employee masters and migration template |
| 4. Leave + attendance | 8-10 weeks | Policies, approvals, device adapter, attendance engine and reports |
| 5. Payroll | 10-12 weeks | Rule engine, advances/PF/gratuity, outputs and parallel-run readiness |
| 6. Accounts | 12-16 weeks | COA, vouchers, ledgers, banks, budget and statements |
| 7. Inventory + member + files | 12-16 weeks, parallel streams | Operational modules, portal, payment and document workflow |
| 8. Integration, migration and system test | 8-10 weeks | Reconciled migrations, performance/security/integration evidence |
| 9. UAT, parallel run and training | 6-8 weeks | Two payroll cycles, financial sign-off, SOPs, trained users |
| 10. Production cutover/hypercare | 4-6 weeks | Go-live, monitored operation, defect closure and handover |

Recommended delivery is **11-14 calendar months** with a balanced 8-person core team and partial specialists. Add 2-3 months if decisions/data are slow or accounting/payroll rules are unusually complex.

---

# 13. Module-Wise Man-Day Estimation

This is the recommended production-ready estimate, not a promise derived from the three-page list alone.

| Workstream/module | Complexity | Frontend MD | Backend MD | Database MD | Testing MD | Total MD |
|---|---|---:|---:|---:|---:|---:|
| Discovery, SRS and solution design | High | 8 | 14 | 8 | 5 | 35 |
| UX design system/prototypes | Medium | 28 | 2 | 0 | 6 | 36 |
| Platform, RBAC, audit and settings | High | 24 | 38 | 12 | 18 | 92 |
| HRM/employee lifecycle | High | 38 | 42 | 14 | 22 | 116 |
| Leave management | Medium-High | 24 | 30 | 8 | 16 | 78 |
| Attendance/device/shift/overtime | High | 32 | 56 | 16 | 28 | 132 |
| Payroll/PF/gratuity/advance | Very High | 38 | 78 | 22 | 42 | 180 |
| Accounts and finance | Very High | 52 | 96 | 30 | 52 | 230 |
| Inventory/stores | High | 32 | 42 | 14 | 24 | 112 |
| Member/billing/payment/portal | High | 46 | 54 | 16 | 30 | 146 |
| File/document management | High | 28 | 36 | 10 | 20 | 94 |
| Notifications/communications | Medium | 12 | 24 | 6 | 12 | 54 |
| Dashboards/reports/exports | High | 44 | 42 | 12 | 26 | 124 |
| External integrations | High | 10 | 42 | 8 | 22 | 82 |
| Migration and reconciliation tools | High | 12 | 28 | 20 | 24 | 84 |
| DevOps, observability, backup and DR | High | 4 | 24 | 10 | 16 | 54 |
| UAT support, training and cutover | High | 12 | 18 | 6 | 24 | 60 |
| **Total** | **Very High** | **444** | **666** | **212** | **387** | **1,709 MD** |

Effort includes engineering and functional testing but not client time. Add **10-15% contingency** to a fixed-price bid until the SRS is signed. A narrower “literal source only” implementation could be approximately **900-1,050 MD**, but would omit controls/capabilities identified in Section 3 and is not recommended as an enterprise ERP commitment.

---

# 14. Total Project Timeline

Pure arithmetic understates elapsed time because analysis, specialist QA, approvals, UAT and parallel payroll cannot be perfectly parallelized.

| Delivery capacity | Arithmetic at 20 MD/person-month | Realistic elapsed duration | Comment |
|---|---:|---:|---|
| Single full-stack developer | 85.5 person-months | **6.5-8 years** | Operationally unsuitable; key-person and quality risk |
| 2 developers | 42.5 months | **40-48 months** | Specialists and client UAT still required |
| 3 developers | 28.4 months | **27-34 months** | Possible staged product, slow enterprise rollout |
| 5 developers | 17.0 months | **18-23 months** | Requires shared QA/BA/DevOps outside the five |
| Recommended cross-functional team | capacity varies | **11-14 months** | 6 engineers/QA plus BA, UX, PM and part-time DevOps/DBA |

If “developer” counts exclude BA, UX, QA, PM and DevOps, their work must not be silently removed from cost or schedule.

---

# 15. Team Recommendation

| Role | Indicative allocation | Responsibility |
|---|---:|---|
| Project Manager/Scrum Lead | 0.6-1.0 FTE | Scope, plan, RAID, governance, acceptance and commercial control |
| ERP Business Analyst/Product Owner proxy | 1.0-1.5 FTE | Process/SRS, accounting/payroll rules, backlog and UAT |
| Solution Architect/Technical Lead | 0.5-1.0 FTE | Architecture, security, quality gates and critical design |
| Backend engineers | 2-3 FTE | Domain, APIs, integrations, jobs and reports |
| Frontend engineers | 2 FTE | Admin ERP and employee/member portals |
| UI/UX designer | 0.5 FTE early, 0.2 later | Research, prototypes, design system and usability |
| QA automation/functional engineers | 2 FTE | Test design, automation, regression, performance and UAT support |
| DevOps/SRE | 0.3-0.5 FTE | CI/CD, environments, monitoring, backup and release |
| DBA/data migration specialist | 0.3-0.7 FTE | Model review, performance, migration and reconciliation |
| Security tester | Time-boxed | Threat review and independent penetration test |
| Trainer/support analyst | 0.5 FTE near launch | SOP, training, cutover and hypercare |

**Core team:** 8-10 people; **peak team:** 11-12; average effective capacity about 7-8 FTE after part-time roles and project overhead.

---

# 16. Budget Estimation

## Basis

1,709 MD × 8 = **13,672 engineering/service hours**. Fixed-price ranges include a risk premium for the incomplete source scope but exclude taxes, hardware, provider usage, licenses, independent audit and post-warranty support. Regional figures represent typical supplier positioning and delivery overhead, not employee salary comparisons.

| Market | Planning hourly/blended rate | Time-and-material estimate | Indicative fixed-price range |
|---|---:|---:|---:|
| Bangladesh | **$25-$45/hr** | **$340k-$612k** | **$390k-$705k** |
| India | **$30-$55/hr** | **$408k-$748k** | **$470k-$860k** |
| Middle East | **$65-$120/hr** | **$885k-$1.63m** | **$1.02m-$1.88m** |
| Europe | **$80-$150/hr** | **$1.09m-$2.04m** | **$1.25m-$2.35m** |
| USA | **$120-$220/hr** | **$1.63m-$2.99m** | **$1.88m-$3.44m** |

Fixed-price midpoint methodology: estimated hours × chosen blended rate, plus approximately 12-18% scope/delivery risk. Local tenders can be lower because of salary economics, but a materially lower bid must reduce scope, quality controls or senior-team availability explicitly.

**Benchmark note.** Rates are planning assumptions triangulated against the broad 2026 freelance range of $20-$150/hour published by [Upwork](https://www.upwork.com/hire/software-developers/) and current regional outsourcing commentary. They are deliberately normalized for an enterprise cross-functional team; vendor brand, on-site presence, liability, compliance and procurement terms can move actual quotations materially.

### Recurring/excluded cost categories

- Hosting/DR, domains/certificates, SMS/email, payment-gateway MDR, object storage/egress and monitoring.
- Attendance devices/networking, bank/provider certification, commercial reporting/UI/security licenses.
- Annual support recommended at **15-20% of implementation price**, with enhancements separately budgeted.
- Major statutory changes, new integrations, native apps and additional organizations are outside baseline.

---

# 17. Proposal Risk Analysis

| Risk | Probability/impact | Mitigation / contractual protection |
|---|---|---|
| High-level document mistaken for complete scope | Very high/very high | Paid discovery; signed SRS/backlog and exclusions before fixed build price |
| Hidden requirements and scope creep | High/very high | Traceability matrix, assumptions, change board and priced rate card |
| Payroll formula/statutory ambiguity | High/very high | Client-owned rule book, worked examples, golden test cases, two parallel cycles |
| Accounting basis/compliance ambiguity | High/very high | Qualified accountant sign-off, COA/statement samples and opening-balance reconciliation |
| Attendance-device incompatibility | High/high | Technical spike using actual device/firmware/network before commitment |
| Poor/duplicate historical data | High/high | Profiling, cleansing ownership, trial loads, control totals and migration acceptance |
| Payment webhook/reconciliation error | Medium/very high | Idempotency, signature verification, settlement match and provider sandbox certification |
| Slow stakeholder decisions | High/high | Named product owner, decision SLA and schedule relief clause |
| Approval/SoD discovered late | Medium/high | Early authority-matrix workshop and finance/security review |
| Report proliferation/layout changes | High/medium | Include named report catalogue and sample; cap custom layouts |
| Infrastructure undersizing | Medium/high | Load model, performance test, monitoring and scalable deployment |
| Security/privacy breach | Medium/very high | Threat model, least privilege, encryption, secure SDLC and independent pen test |
| Backup exists but restore fails | Medium/very high | Automated verification and witnessed restore/DR drill |
| User adoption/resistance | Medium/high | Super users, prototypes, training, SOP and phased rollout |
| Key-person dependency | Medium/high | Code review, documentation, pairing and cross-training |
| Vendor/API changes | Medium/medium | Adapter boundaries, contract tests and support/change clause |
| Fixed-price currency/inflation exposure | Medium/high | USD/BDT basis date, validity period and adjustment clause for long delays |

---

# 18. Questions to Ask the Client

## Governance and scope

1. What legal entities, foundations, branches and locations must the system support?
2. Is BIA Foundation a separate accounting entity or a fund/cost center within BIA?
3. Who is the empowered product owner and who signs each module acceptance?
4. Which current systems, spreadsheets and manual registers will be replaced?
5. Which features are mandatory for first go-live versus later phases?
6. Is Bangla UI/data/reporting required, and which content must be bilingual?
7. Are native mobile apps, offline work or only responsive web pages required?
8. What user, employee, member, transaction, document and concurrent-user volumes exist today and in five years?
9. What availability, maintenance window, performance, RPO and RTO are required?
10. What regulations, IDRA directions, accounting standards and internal policies are binding?

## HR, leave and attendance

11. What employee categories, grades, scales, branches and employment statuses exist?
12. Which employee fields/documents are mandatory and who may view sensitive fields?
13. What promotion, transfer, increment, confirmation and separation workflows apply?
14. Which leave types, eligibility, accrual, carry-forward, expiry and encashment rules apply?
15. Are half-day, hourly, negative, maternity/paternity and medical-document rules needed?
16. How many approval levels apply, and are delegation/escalation/substitute rules required?
17. What attendance device brands, models, firmware, SDK/API and network topology are in use?
18. How are employee IDs mapped between devices and HR records?
19. What shift, roster, grace, cross-midnight, holiday and weekend rules apply?
20. How are missing punches, field duty, work from home and manual corrections authorized?
21. How are late, extra-late, early exit and absence converted into payroll deductions?
22. What overtime eligibility, approval, rounding, ceiling and rate formulas apply?

## Payroll, PF, gratuity and tax

23. Provide every earning/deduction formula with effective date and worked examples—who owns sign-off?
24. Is payroll monthly only, and are multiple payroll groups/cut-off dates required?
25. How are joining, separation, unpaid leave, arrears, bonus and retroactive changes prorated?
26. What salary scales, steps, increments and revision histories must be supported?
27. What advance/loan types, interest, installment and final-settlement rules apply?
28. What employee/employer PF rates, eligibility, interest allocation and withdrawal rules apply?
29. What gratuity eligibility, service rounding, provisioning and settlement formula applies?
30. Must the system calculate Bangladesh income tax and generate certificates/returns?
31. Which bank upload formats, cheque/cash formats and payslip templates are required?
32. How many historical payroll years must be migrated?
33. Who prepares, checks, approves, locks and may reopen payroll?
34. How many successful parallel payroll cycles constitute acceptance?

## Accounts and inventory

35. Is accounting cash, accrual or mixed, and what fiscal year/period-close process applies?
36. Provide the approved chart of accounts, cost centers, funds/projects and opening trial balance.
37. Which vouchers and approval limits are required, including maker-checker restrictions?
38. Are AP, AR, procurement, budget, fixed asset, VAT and withholding tax in scope?
39. Which financial statements and regulator-specific formats must exactly match samples?
40. How many bank accounts, currencies, cheque books and reconciliation formats exist?
41. How does member billing post into the general ledger and recognize income?
42. How must payroll and inventory transactions post to accounts and cost centers?
43. How many stores/warehouses/bins and item categories are required?
44. Is purchase requisition, quotation/tender, PO and supplier bill processing required?
45. Which valuation method—weighted average, FIFO or another—must be used?
46. Are serial, batch, warranty, expiry, barcode and fixed-asset capitalization required?
47. Who can approve stock adjustment, loss, disposal, transfer and return?

## Members, files, integrations and operations

48. What member types, onboarding approval, renewal, suspension and termination rules apply?
49. How are fees calculated—recurring cycle, prorating, arrears, waiver, penalty and tax?
50. Which payment gateway and merchant account will be used; are refund and partial payment needed?
51. Can a member have multiple portal users/branches, and what may each representative see?
52. What member certificate/card, invoice, receipt and statement templates are required?
53. What exactly constitutes IDRA, Ministry, SBC, NBR, ICC and FBCCI “information”?
54. Is file management a correspondence register, document repository, workflow system or all three?
55. What confidentiality classes, retention schedules, legal holds and disposal approvals apply?
56. Is OCR/full-text search required, and what document formats/maximum sizes are allowed?
57. Which SMS/email providers, sender IDs, quotas and approved templates exist?
58. Is Active Directory/Entra SSO mandatory, and which groups map to ERP roles?
59. Must backups go specifically to Google Cloud; who owns the project, keys and recurring cost?
60. What environments are required and will hosting be on-premises, cloud or hybrid?
61. Who provides devices, network/VPN/firewall rules, domains, certificates and provider credentials?
62. What source formats, record counts and data-quality issues exist for migration?
63. Who cleans source data and signs control totals, opening balances and migrated history?
64. What audit-log retention and privileged-access review frequency is required?
65. What penetration testing, source-code handover, escrow and security certification are required?
66. What browsers, accessibility standard and office/report software must be supported?
67. What training groups, locations, manuals, videos and train-the-trainer sessions are required?
68. What warranty, support hours, response/resolution SLA and on-site presence are expected?
69. What are the acceptance criteria, severity definitions and deemed-acceptance timeline?
70. What change-request, delay, dependency and termination terms will govern the contract?

---

# 19. Proposal Recommendation

| Offer tier | Scope posture | Budget (Bangladesh delivery) | Timeline |
|---|---|---:|---:|
| Minimum viable controlled ERP | Core stated modules, essential audit/RBAC; limited reports/integrations/migration | **$300k-$375k** | **10-12 months** |
| Recommended enterprise baseline | Scope in this report, named integration caps, 2 migration trials and 2 parallel payroll cycles | **$450k-$575k** | **11-14 months** |
| Premium/resilient program | Baseline plus HA/DR, deeper procurement/assets/tax, more automation, performance/security assurance | **$650k-$850k+** | **14-18 months** |

**Minimum budget recommendation:** do not bid below **$300,000** without explicitly reducing scope.  
**Recommended budget:** **$495,000 fixed price** after paid discovery and signed SRS.  
**Premium budget:** **$750,000** for broader finance/procurement, resilience and extended assurance.  
**Minimum credible timeline:** 10 months with rapid decisions and controlled scope.  
**Recommended timeline:** 12-14 months.  
**Ideal low-risk timeline:** 15-16 months including stabilization and two completed parallel payroll cycles.

---

# 20. Final Bid Recommendation

For a senior ASP.NET Core enterprise ERP developer with 13+ years’ experience, bid as a solution lead backed by a delivery team—not as a solo coder.

| Recommendation | Position |
|---|---|
| **Best fixed price** | **$495,000** for the defined enterprise baseline, subject to discovery/SRS scope gate |
| **Best hourly rate** | **$45/hour individual senior lead**; **$36-$42/hour blended team rate** |
| **Total effort** | **1,709 MD / 13,672 hours**, with -20%/+25% ROM range before SRS |
| **Team size** | **8-10 core, peak 11-12**, approximately 7-8 effective FTE average |
| **Proposal strategy** | Sell a paid discovery followed by a re-baselined implementation; attach assumptions, exclusions, deliverables and traceability matrix |
| **Negotiation strategy** | Negotiate scope before rate; offer phased options, cap integrations/reports/migration cycles, and trade discounts only for reduced risk or advance payment |
| **Scope definition** | Signed SRS/backlog, process diagrams, data dictionary, report samples, NFRs, integration specs and acceptance tests form the baseline |

## Milestone and payment schedule

| Milestone | Acceptance evidence | Payment |
|---|---|---:|
| Contract mobilization | Kick-off, project plan, governance | **10%** |
| Discovery/SRS/architecture | Signed SRS, prototype, NFR and release plan | **15%** |
| Platform + HRM + leave | Demonstrated release and agreed tests | **15%** |
| Attendance + device integration | Actual-device acceptance and attendance reports | **12%** |
| Payroll | Golden cases, outputs and first parallel cycle | **15%** |
| Accounts | Posting controls and agreed statements reconcile | **15%** |
| Inventory + member + file modules | Integrated UAT release | **10%** |
| Migration, security/performance and final UAT | Signed UAT and cutover readiness | **5%** |
| Production go-live and hypercare | 30-day stable operation and handover | **3%** |
| **Total** |  | **100%** |

Prefer milestone acceptance within 10 business days, with one consolidated defect list and deemed acceptance for unexplained delay. Retention, if mandatory, should be no more than 5% and released after a defined 60-90 day warranty—not an open-ended support period.

## Commercial protections and exclusions

- Quote validity: 30 days; USD basis or an exchange-rate adjustment mechanism.
- Fixed price activates only after SRS approval; until then discovery is time-and-material or separately fixed.
- Include one attendance-device model, one SMS provider, one payment gateway, one email service, one bank-file format, two trial migrations and the named report catalogue.
- Exclude hardware, network remediation, cloud/provider charges, data cleansing, native apps, OCR licenses, new statutory interpretations, undocumented legacy interfaces and 24×7 support unless priced.
- Client dependencies must carry schedule relief: timely decisions, SMEs, actual devices, samples, clean data, credentials, infrastructure and UAT resources.
- Changes use written impact assessment at the agreed blended rate plus schedule adjustment.

## Executive bid position

The commercially strongest position is a **$495,000, 12-14 month phased bid**, preceded by a paid 4-6 week discovery and delivered by an 8-10 person core team. If BIA’s available budget is materially lower, propose a Phase 1 comprising platform/RBAC, HRM, leave, attendance and core payroll, then price Accounts, Inventory, Member and File Management as subsequent releases. Do not promise the full production-grade system at a small-website price or a solo-developer schedule.

---

# Assumptions, Confidence and Estimation Controls

## Included assumptions

- One BIA tenant/legal organization plus BIA Foundation treatment to be confirmed.
- Responsive web application; modern evergreen browsers; no native mobile/offline mode.
- One production language at launch with architecture ready for localization.
- One device model/provider for each named integration unless otherwise stated.
- Standard business-hours support during delivery and a defined hypercare/warranty period.
- Client supplies approved policies, formulas, report samples, opening balances and test users.
- Up to two migration rehearsals plus final cutover; source data delivered in agreed templates.
- Automated tests prioritize financial/payroll rules, permissions and critical workflows rather than 100% line coverage.

## Confidence by area

| Area | Confidence | Reason |
|---|---|---|
| Named modules | Medium | Clearly listed but shallow |
| Payroll/accounts effort | Low-Medium | Rules, compliance and outputs absent |
| Attendance integration | Low | Device/vendor/protocol absent |
| Member/payment | Low-Medium | Billing rules and gateway absent |
| File management | Low | Only six headings are provided |
| Architecture | Medium-High | Standard enterprise pattern; NFRs still unknown |
| Budget/timeline | ROM only | Must be re-estimated after discovery |

## Required proposal attachments

Scope traceability matrix; assumptions/exclusions; responsibility (RACI) matrix; milestone deliverables; acceptance procedure; change-control form; rate card; integration caps; migration plan; report catalogue; NFR schedule; security schedule; support SLA; IP/source-code terms; and commercial validity/tax terms.

---

*End of report.*
