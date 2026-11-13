# 09 · Analytics and Iteration

## Product analytics questions

- How often does a verified downtime event produce a recovery proposal?
- How long does it take from verified event to feasible proposal and then to applied schedule?
- How often do planners apply, edit, defer, or reject proposals—and why?
- Which inputs are stale or unavailable, and how often does that block recovery?
- Do affected jobs meet customer delivery commitments after recovery?
- Does the new workflow increase or reduce schedule churn?

## Choosing an analytics framework

The **AARRR** funnel (Acquisition, Activation, Retention, Referral, Revenue) is useful when product-led acquisition or growth is a core product motion. It is not the primary framework for this enterprise scheduling workflow. Use workflow adoption and operational outcome measures here; add AARRR only if Amtech is evaluating a self-serve growth or commercial funnel question.

Treat product analytics as a loop across discovery, delivery, release, and iteration. Define outcome and guardrail measures before the pilot, instrument the needed events during development, and review results after rollout.

## Candidate events

| Event | When to record | Key properties |
|---|---|---|
| `downtime_verified` | Disruption is confirmed by the workflow | Resource type, event category, event timestamp |
| `proposal_generated` | Recovery proposal is generated | Proposal version, affected-job count, generation time, input freshness |
| `proposal_viewed` | Authorized user opens proposal details | Proposal version, elapsed time since event |
| `proposal_applied` | Proposal successfully becomes current schedule | User role, proposal version, elapsed time, constraint status |
| `proposal_edited` | User changes a proposed sequence or assignment | Edit category, reason where provided |
| `proposal_deferred` | User postpones decision | Reason category where provided |
| `proposal_failed` | No feasible result or system/data failure occurs | Failure category, blocking constraint category |
| `schedule_changed_after_apply` | A further change is applied after recovery | Time since apply, reason category |

Use stable, documented event definitions. Avoid raw customer names, unnecessary user data, and sensitive details in analytics events. Confirm applicable data policies and customer configuration before instrumentation.

## Measurement funnel

Verified event → proposal generated → proposal reviewed → proposal applied/edited/deferred → schedule outcome observed.

Report each transition and elapsed time, not only proposal generation or screen opens. A high proposal-application rate is not automatically success if users feel pressured or outcomes worsen.

## Pilot analysis

- Compare each pilot workflow with its own baseline using the same metric definitions.
- Segment by resource, disruption type, plant configuration, and customer-defined due-date rules where data volume supports it.
- Review qualitative override and defer reasons alongside quantitative measures.
- Check for selection bias and changing disruption mix before attributing changes to the feature.
- Monitor customer delivery, constraint compliance, stale input, and schedule churn guardrails.

## Iteration cadence

Review pilot data and customer feedback with Product, Engineering, UX, QA, Support, Implementation, and Analytics on an agreed cadence. Convert repeated issues into backlog items, update assumptions and documentation, and make an explicit expand/revise/stop recommendation. Revisit the objective and metric definitions if customer workflows reveal that another outcome is more important.

