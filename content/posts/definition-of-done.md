---
title: "Definition of Done"
date: 2023-08-20T21:11:31+01:00
tags: ["agile", "teamops"]
---

## Definition of Done

One thing that I've noticed in common across the various teams I've worked in, is that teams like to create a *definition of done* to look at to see whether a ticket is actually completed. I've also found them hard to come by online, so here's my current version.

> tl;dr: We built the right thing, we built the thing right, it's documented and deployed.

#### We built the right thing…

- Acceptance criteria met
- Bugs fixed or accepted by PO
- Demoed to customer
- Metrics/telemetry gathered to prove value/hypothesis

#### We built the thing right…
- Followed best practices
   - Static analysis tooling run on source code (including IAC)
   - Dependencies are resilient / fault tolerant
   - There is Excellent Alerting™ (*more on this in another post*)
   - All cloud infrastructure in Terraform
   - We considered backups / DR
   - Code was peer reviewed
   - Feature switches were used
   - Refactoring complete
   - Accepted tech debt audited
- It’s GDPR compliant
   - Personal data is encrypted at rest, between nodes, and in transit via HTTPS etc
   - No PII is stored in logs
   - We have considered how a Right to be Forgotten / Right to Access request would be considered
   - We’ve understood, documented and logged personal information stored, and considered it in all pillars of GDPR compliance
- It's tested:
   - Unit tests / integration tests / end to end tests complete. Coverage is acceptable.
   - Automated E2E tests are running in the pipeline
   - Chaos tests carried out to prove resilient dependencies
   - Performance tests if necessary
   - Accessibility tests considered where appropriate
   - Manual testing completed where necessary

#### it's documented…
- ADRs are written
- APIs are documented with Swagger
- Architecture diagrams are done
- `Readme.md` reflects the state of the repo
- An outage runbook is included with Excellent Alerting™
- Comms out to users with screenshots and summaries

#### …and deployed
- Automatically deployed through a pipeline
- Running in Production
- Post-deploy smoke tests have run and passed

## Some after-thoughts on a Definition of Done, or how to go about creating your own
I've found teams oftentimes struggle with consistently applying these definitions, they're generally set in some kind of an early-days *team charter* meeting, maybe at the end of a long week of such sessions, written in a wiki somewhere then forgotten about; gathering dust.

It can also seem like 'another thing' to have to do, *another meeting*. "Right team, let's come up with our definition of done!" isn't always particularly motivating to a bunch of engineers who just want to get on and write some code.


If you've noticed this happening to you or your team, I suggest you apply the same principles you'd apply to any ticket coming through your board: slice it! 

### Start with one thing
There must be one thing that the team agree on, for a ticket to be done.

> - It's deployed

May be a good starting point. Most teams would agree that for a thing to be done, it has to be deployed. Once you've got that established, you can start to ask coaching question of the team:

> "*and what would we want to make sure of before we deployed it?*"

This should (hopefully) spark some discussion and ideas - and it's from this point that you can start to build your team's Definition of Done.