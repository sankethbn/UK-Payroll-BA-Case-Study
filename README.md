# UK Payroll Platform: Business Analyst Case Study

A personal case study I wrote to practise end-to-end Business Analyst work on a domain with strict rules. It is not work done for a company or a real client. The scenario, documents, stories and test cases are all my own.

## The scenario

A UK employer wants a platform to run payroll for its staff: salary runs, payslips, leave and attendance, PAYE, National Insurance and pension auto-enrolment. In my scenario, development has already started, but nobody owns the requirements. Some rules only exist in the code or in people's heads. A few have been built differently from how HR expects them to work.

I picked payroll because the rules are public (HMRC and pension guidance) and unforgiving. A vague requirement here means someone gets paid the wrong amount.

## What I did

**Started with a gap analysis.** I listed what a half-built system would typically have, compared it with what HR actually needs and wrote down the rules that were missing or unclear.

**Wrote the BRD and FRD.** The [BRD](BRD.md) covers the why and the what: objectives, scope, stakeholders, business requirements and the UK rules the system has to follow. The [FRD](FRD.md) covers the how: user roles, process flows, functional requirements, business rules, user stories with acceptance criteria and a UAT plan.

**Mapped the flows.** I drew the payroll-run and leave-to-pay process flows so the whole process can be seen in one place.

**Planned UAT.** I wrote sample test cases with worked examples and expected results, covering cases like a mid-month starter, unpaid leave, a Week 1/Month 1 tax code and a pension opt-out.

## Documents

- [Business Requirements Document (BRD)](BRD.md)
- [Functional Requirements Document (FRD)](FRD.md)

## Tools this is written for

The documents are set up the way I would run them in Jira and Confluence, with flows that could become Figma screen reviews and UAT cases that could be checked with SQL against expected payroll outputs.

## What I took away from it

- On a project that is already moving, the first job is listening, not writing. A gap analysis tells you more than any kickoff.
- In payroll, "we all know how that works" is usually where the disagreements hide. Writing each rule down and getting it confirmed saves the most rework.
