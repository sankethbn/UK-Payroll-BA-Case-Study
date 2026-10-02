# UK Payroll Platform: Business Analyst Case Study

- **Company:** Logic Lumin Software
- **Role:** Business Analyst (Jan 2026 to present)
- **Client:** a UK payroll client (name withheld under NDA)

I joined a live UK HR and payroll build partway through, as Logic Lumin's first and only Business Analyst. Development was already running, but nobody owned the requirements. A lot of the business rules only existed in people's heads or in the code itself. This repo explains how I approached that and what came out of it.

> **About confidentiality.** The client's name and documents are confidential. The BRD and FRD in this repo are rewritten from scratch for my portfolio. They follow the structure I used on the project and standard UK payroll rules, but they contain no client data, names or figures.

## The situation

The platform handles payroll for UK employees: salary runs, payslips, leave and attendance, PAYE, National Insurance and pension auto-enrolment. When I joined, there was no single place that said what the system should do. Some rules had never been written down. Others had been built differently from how the client expected them to work.

## What I did

**Gap analysis first.** Before writing anything new, I compared what had already been built with what the client actually needed. That surfaced undocumented business rules, process gaps and places where the build didn't match the client's expectations. Where a rule wasn't written down anywhere, I traced how the system currently behaved, checked it with the client and wrote down the agreed version.

**Owning the requirements.** From there I took over requirements across salary runs, payslips, leave and attendance, PAYE, National Insurance and pension auto-enrolment. I wrote and maintained the BRD and FRD in Confluence so the team had one source of truth.

**Stories and sprints.** I broke the requirements down into 30+ user stories with acceptance criteria in Jira and worked them through our sprints with the client's HR team and our Development Manager.

**Flows and design reviews.** I mapped the payroll-run and leave-to-pay process flows and walked the client through the Figma screens before development started. Catching a workflow problem on a screen is a lot cheaper than catching it in a finished feature.

**UAT.** I wrote 40+ UAT test cases in Excel and checked payroll outputs with SQL against the expected results. That caught around a dozen defects before release.

## Results

| What | Roughly |
| --- | --- |
| User stories written in Jira | 30+ |
| UAT test cases written | 40+ |
| Defects caught before release | About a dozen |

## Documents

- [Business Requirements Document (BRD)](BRD.md): the why and the what. Background, objectives, scope, stakeholders, business requirements and UK rules the system has to follow.
- [Functional Requirements Document (FRD)](FRD.md): the how. User roles, process flows, functional requirements, business rules, sample user stories with acceptance criteria and the UAT approach.

## Tools I used

Jira for the backlog and sprints, Confluence for the BRD and FRD, Figma for screen reviews with the client, Excel for UAT test cases and SQL for checking payroll outputs.

## What I took away from it

- Joining mid-project means the first job is listening, not writing. The gap analysis told me more about the project than any kickoff would have.
- In payroll, "we all know how that works" is usually where the disagreements hide. Writing a rule down and getting the client to confirm it saved more rework than anything else I did.
