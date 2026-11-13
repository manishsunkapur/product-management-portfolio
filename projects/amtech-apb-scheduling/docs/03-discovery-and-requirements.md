# 03 · Discovery and Requirements Gathering

## Discovery objective

Learn how scheduling teams detect, evaluate, approve, and communicate a recovery plan after an unexpected production disruption. Establish the problem’s frequency and cost, understand current APB behavior, and capture operational constraints before recommending features.

## Stakeholders to involve

| Stakeholder | What to learn |
|---|---|
| Production scheduler / planner | Decisions, workarounds, trust needs, priority rules |
| Plant or shift manager | Approval rights, escalation, schedule stability, operating risk |
| Machine operators / supervisors | How events are reported; what schedule changes are visible and usable |
| Customer service / shipping | How order and dispatch commitments are affected |
| Implementation / Support | Configuration differences, recurring cases, existing workarounds |
| Product / UX / Engineering / QA | Current capabilities, workflow constraints, dependencies, test coverage |
| Analytics / Data | Available event, schedule, order, and production outcome data |

## Research activities

1. **Internal capability review:** Walk through APB’s current downtime and rescheduling behavior with Product, Engineering, Support, and Implementation. Map what is configurable and where product versions differ.
2. **Customer interviews:** Use recent incidents, not general opinions. Ask the scheduler to reconstruct a specific event and decision.
3. **Workflow observation:** Where permitted, observe a planning or shift handoff and map tools, data checks, decision rights, and communications.
4. **Operational evidence review:** Inspect anonymized schedule changes, support cases, event timestamps, overrides, and order outcomes where available.
5. **Segmentation:** Compare workflows across corrugated plant types, resource complexity, schedule maturity, and customer configurations.
6. **Market and alternatives review:** Learn how customers solve the same job today (existing ERP/MES features, spreadsheets, other systems, manual coordination) and compare public alternatives only where it informs differentiation or expectations.
7. **Prototype research:** Test whether a scheduler understands and trusts the information needed to make a recovery decision.

## Interview guide

- Walk me through the most recent unplanned stop that changed an active lineup.
- How did you learn about the stop, and how did you know the status was current?
- What did you do first? What information did you check next?
- Which jobs and constraints mattered most? How did you make those trade-offs?
- What did APB handle, and where did you use another tool, contact a colleague, or make a manual change?
- Who could approve or publish the new lineup? How did other shifts learn about it?
- How did you know the recovery was successful? What was the operational or customer impact?
- What would make a proposed schedule unsafe or unacceptable?

Avoid pitching the solution before the participant explains the workflow. Ask for examples, artifacts, and the last occurrence to reduce hypothetical answers.

## Evidence log template

| Date / source | Workflow observed | User quote or behavior (anonymized) | Pain / impact | Confidence | Follow-up |
|---|---|---|---|---|---|
| To be completed in discovery | — | — | — | Not validated | — |

## Opportunity Solution Tree (OST)

Use an Opportunity Solution Tree after discovery to connect the agreed outcome to user opportunities, candidate solutions, and experiments. Do not use it as a substitute for evidence or as a static requirements document.

```text
Outcome: reduce time to a confirmed feasible recovery schedule
└── Opportunity: understand what changed in the active lineup
    ├── Solution: current/proposed schedule comparison
    └── Experiment: prototype task—identify changed jobs without help
└── Opportunity: trust event and schedule inputs
    ├── Solution: show event status and input freshness
    └── Experiment: stale-input prototype scenario
└── Opportunity: understand delivery and setup trade-offs
    ├── Solution: impact summary and proposal rationale
    └── Experiment: ask planners to explain the main trade-off
```

All branches above are illustrative until validated with users.

## Candidate requirements

Requirements below are discovery prompts and candidate requirements, not approved product scope.

### Functional requirements

| ID | Candidate requirement | Validation question |
|---|---|---|
| FR-01 | Associate a disruption with the affected resource and active schedule | How are event identity, duration, and status represented today? |
| FR-02 | Show the current inputs and their last-updated time | What data source and freshness are meaningful to planners? |
| FR-03 | Show a proposed schedule and identify jobs/resources that changed | What is the minimum useful comparison? |
| FR-04 | Explain due-date, setup, downstream, and hard-constraint impacts | Which impacts drive the decision, and how are they calculated? |
| FR-05 | Let authorized users apply, adjust, or defer a proposal | What roles and approval rules differ by plant or shift? |
| FR-06 | Preserve decision history and current schedule version | What audit and handoff history is required? |
| FR-07 | Explain when no feasible proposal is available | What constraints should be shown, and which can be safely disclosed? |
| FR-08 | Handle stale, conflicting, duplicate, or cleared disruption events | What states can occur and how should the system recover? |

### Quality and operational requirements

- **Trust:** Clearly distinguish confirmed facts, estimated timing, and assumptions.
- **Data freshness:** Do not silently treat outdated production or schedule inputs as current; exact thresholds must be set with Engineering and customers.
- **Permissions:** Respect the customer’s roles and approval process.
- **Security and data handling:** Respect customer data boundaries, least-privilege access, and applicable company security controls; confirm exact requirements with Amtech teams.
- **Traceability:** Record the proposal version and user action where required for shift handoff and support.
- **Performance:** Agree on response-time expectations with Engineering based on the scheduling workflow and plant configuration.
- **Resilience:** Preserve the last confirmed schedule and provide a clear path when the service or inputs are unavailable.
- **Usability and accessibility:** Make the most important trade-offs understandable under time pressure, at the screen sizes used in plants, and with accessible interaction and contrast.

## Requirement readiness checklist

Before an item enters a sprint, confirm the user and outcome, user evidence, business rule, edge cases, data source, permission model, acceptance criteria, analytics needs, design reference, and dependencies. Open questions should be visible and assigned rather than hidden in a story.

## Framework fit

- Use **JTBD** and contextual interviews to frame user progress and triggers.
- Use **5 Whys** to investigate an individual event, then triangulate.
- Use an **Opportunity Solution Tree** to organize validated opportunities, options, and experiments.
- Gather requirements from workflows, rules, exceptions, data, and roles—not only from requested features.
