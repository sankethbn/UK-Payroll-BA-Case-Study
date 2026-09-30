# UK Payroll Platform: Business Requirements Document

Portfolio version · Prepared by Basava Sanketh B N (Business Analyst) · Logic Lumin Software

See also: [FRD](FRD.md) · [Project overview](README.md)

> This is a rewritten sample for my portfolio. It follows the structure I used on the project and standard UK payroll rules. It contains no client names, data or figures.

---

## 1. Purpose

This document describes what the business needs from the payroll platform and why. It is the reference point for scope decisions. The [FRD](FRD.md) turns each business requirement into functional detail.

## 2. Background

The client runs payroll for UK employees. The platform replaces manual steps around salary runs, payslips and leave. It has to follow HMRC rules for PAYE and National Insurance as well as workplace pension law.

Development had already started before a Business Analyst joined. Several business rules existed only in the code or in conversations, so the first step was a gap analysis to capture what had been built and confirm what the client actually needed.

## 3. Objectives

| # | Objective |
| --- | --- |
| O1 | Run accurate payroll every pay period with correct PAYE, National Insurance and pension deductions |
| O2 | Give every employee a clear itemised payslip for each pay period |
| O3 | Make sure leave and attendance flow into pay without manual re-keying |
| O4 | Assess and enrol eligible employees into a workplace pension automatically |
| O5 | Keep one agreed, written set of business rules that development and testing both work from |

## 4. Scope

**In scope**

- Employee pay setup (salary, pay frequency, tax code, NI category)
- Payroll runs: calculation, review, approval and closing a pay period
- Payslips
- Leave and attendance, including how they affect pay
- PAYE income tax
- National Insurance contributions
- Pension auto-enrolment

**Out of scope for this document**

Anything not listed above, such as expenses, benefits reporting and non-UK payroll.

## 5. Stakeholders

| Who | Interest | Involvement |
| --- | --- | --- |
| Client HR team | Accurate pay, less manual work, compliance | Requirements, design reviews, UAT, sign-off |
| Development Manager | Clear, buildable requirements | Feasibility, sprint planning, delivery |
| Development team | Unambiguous stories and acceptance criteria | Build and fix |
| Business Analyst | One traceable set of requirements | Owns BRD, FRD, backlog and UAT |
| Employees | Being paid correctly and on time | End users of payslips and leave |

## 6. UK rules the system must follow

These come from public HMRC and pensions guidance and apply to any UK payroll.

- The tax year runs from 6 April to 5 April.
- Income tax is deducted through PAYE using each employee's HMRC tax code, normally on a cumulative basis unless the code is marked Week 1/Month 1.
- National Insurance is worked out per pay period using the employee's NI category letter.
- Pay and deductions are reported to HMRC through Real Time Information (RTI) on or before each payday.
- Workers are entitled to an itemised payslip. Where pay varies with time worked, the payslip shows the hours.
- Employers must assess staff for pension auto-enrolment. Workers aged 22 to State Pension age earning over £10,000 a year are enrolled automatically. Minimum contributions are 8% of qualifying earnings in total, with at least 3% from the employer.
- Employees who opt out within one month get their contributions refunded. Opted-out staff are re-assessed every three years.
- Payroll records are kept for at least three years after the end of the tax year they relate to.

## 7. Business requirements

Priority uses MoSCoW (Must, Should, Could, Won't).

| ID | Requirement | Priority | Objective |
| --- | --- | --- | --- |
| BR-01 | HR can set up and maintain each employee's pay details, tax code and NI category. | Must | O1 |
| BR-02 | The system calculates gross pay for each pay period, including pro-rata pay for starters and leavers. | Must | O1 |
| BR-03 | The system calculates PAYE and National Insurance for every employee each pay period. | Must | O1 |
| BR-04 | The system assesses every employee for pension auto-enrolment each pay period and deducts contributions for members. | Must | O4 |
| BR-05 | Approved leave and recorded attendance feed into the payroll run automatically. | Must | O3 |
| BR-06 | HR reviews and approves a payroll run before it is closed. | Must | O1 |
| BR-07 | Every employee gets an itemised payslip for each pay period. | Must | O2 |
| BR-08 | Corrections to a closed pay period are handled through a controlled, logged process. | Must | O1, O5 |
| BR-09 | HR can see a summary of each run (totals, deductions, exceptions) before approval. | Should | O1 |
| BR-10 | Employees can view past payslips themselves. | Could | O2 |

## 8. Assumptions and constraints

- UK tax, NI and pension thresholds change each tax year, so they must be configurable rather than hard-coded.
- The client's HR team is available for rule confirmation and UAT within each sprint.
- Development was already in progress, so requirements had to be captured alongside ongoing delivery.

## 9. Risks

| Risk | Impact | Mitigation |
| --- | --- | --- |
| Undocumented rules built differently from what the client expects | High | Gap analysis, then confirm every rule with the client in writing |
| Incorrect deductions reaching employees | High | UAT with worked examples, output checks in SQL |
| Threshold changes at the start of a tax year | Medium | Configurable rates with a yearly review |
| Late changes from the client mid-sprint | Medium | Change requests logged in Jira and prioritised with the Development Manager |
