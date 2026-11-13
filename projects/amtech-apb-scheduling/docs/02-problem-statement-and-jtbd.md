# 02 · Problem Statement and JTBD

## Case boundary

This work sample explores downtime-driven schedule recovery in a corrugated packaging plant using a scheduling product such as Amtech APB. Amtech publicly describes APB as supporting automated scheduling and downtime response. That establishes product relevance; it does not establish a customer pain point or a missing capability.

## Problem hypothesis

When an unplanned stop affects a converting resource during an active lineup, a production scheduler may need to quickly determine whether a revised schedule is feasible and what it means for affected jobs, due-date risk, setup changes, and downstream work. The current decision may require effort across multiple views or tools, but this must be confirmed through discovery.

## Problem statement

**Production schedulers at corrugated plants need a fast, trustworthy way to evaluate schedule changes after a converting-resource disruption, so they can restore a feasible lineup while protecting customer commitments and avoiding unnecessary schedule churn.**

This is a testable starting statement. Research may change the user, situation, pain, or desired outcome.

## Who / when / why

- **Primary user:** Production scheduler or planner responsible for an active converting lineup.
- **Trigger:** A production resource becomes unavailable or its expected output changes while work is scheduled.
- **Desired progress:** Understand a feasible recovery path, make a decision, and get the current lineup to the people who need it.
- **Possible secondary users:** Plant/shift manager, operators, customer service, and shipping teams.
- **Business outcome hypothesis:** Reduce time to a confirmed feasible recovery schedule without harming delivery performance or increasing avoidable schedule changes.

## Jobs to be Done (JTBD)

**When** a converting resource unexpectedly becomes unavailable during an active lineup, **I want to** understand which recovery schedule is feasible and what it changes, **so I can** restore production while protecting customer commitments and keeping the floor on a clear plan.

This is a draft JTBD statement to validate with schedulers. In interviews, use the participant’s words and learn about functional, coordination, and confidence needs rather than leading with this wording.

## 5 Whys as a research aid

Apply 5 Whys to one observed incident to explore why the current recovery process took time or created risk. Treat the result as a hypothesis, not proof of a single root cause: production disruptions can have several interacting causes across data, constraints, people, and systems. Validate causes with other users, observations, and operational evidence.

## What we know and do not know

| Item | Status | How to verify |
|---|---|---|
| Amtech offers automated scheduling products for packaging operations | Public product context | Amtech role and APB pages; confirm current ownership internally |
| APB responds to downtime as part of scheduling | Public product context | Review current behavior with Product and Implementation |
| Schedulers struggle to understand proposal impact | Unvalidated hypothesis | Interviews, observation, usability test |
| Manual recovery time is material | Unknown | Establish event timestamps and customer baseline |
| Schedule instability or late-order risk is caused by the workflow | Unknown | Analyze affected orders and compare with customer baseline |
| Needed event and production data are reliable and timely | Unknown | Engineering/data feasibility review |

## Opportunity statement

If discovery confirms that understanding and acting on downtime-driven reschedules is a repeated, costly job, improve the recovery decision workflow so schedulers can see the relevant impacts, choose an action, and maintain a clear current schedule.

## Non-goals for this case

- Claiming that Amtech’s product has a defect or lacks schedule recovery.
- Designing a generic ERP replacement or unrelated machine-vision feature.
- Assuming one scheduling policy works for every plant.
- Promising AI, autonomous rescheduling, or a business result before evidence exists.

## Decision gate

Proceed to a prototype only if discovery confirms a repeated user need, the current product does not already solve it adequately for the target workflow, required data can be trusted, and the outcome can be measured safely in a customer pilot. Otherwise, revise the problem statement or select a different validated opportunity.

