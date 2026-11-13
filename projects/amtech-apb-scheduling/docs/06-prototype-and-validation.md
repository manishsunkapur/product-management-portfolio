# 06 · Prototype and Validation

## Prototype objective

Test whether a production scheduler can understand the change from the current lineup to a proposed recovery, judge its important trade-offs, and make a deliberate decision. The prototype is not intended to prove that the scheduling algorithm is feasible or that a product gap exists.

## Framework fit

Use an iterative **Design Thinking** loop—understand the workflow, frame the user need, explore options, prototype, and test—rather than treating the prototype as a final specification. For UX measurement, **HEART** can help select relevant experience signals. In this operational workflow, emphasize Task Success and, if meaningful, user confidence; do not substitute UX measures for recovery time, delivery, feasibility, and schedule-stability outcomes.

HEART stands for **Happiness, Engagement, Adoption, Retention, and Task Success**. Use only dimensions that answer a real question; Task Success is the closest fit for this workflow.

## Prototype contents

- An illustrative downtime event with event and input freshness.
- A comparison between current and proposed job sequence/resource/time.
- An explanation of why the proposed schedule changed and the key trade-off.
- Due-date risk, additional setup, and constraint information.
- Apply, adjust, and defer actions.
- Exception states for stale inputs and no feasible proposal.
- A visible schedule version and applied/deferred state.

## Clickable concept

Open [`../prototype/index.html`](../prototype/index.html) in a browser. All customers, jobs, times, and schedule outcomes are fictional. The mock-up is independent and should not be represented as Amtech’s actual UI.

## Test participants and method

Recruit production schedulers/planners who regularly work with corrugated converting schedules, ideally across a range of plant complexity and scheduling experience. Include a plant manager or shift supervisor to validate approval and handoff. Conduct moderated sessions with a scenario and think-aloud tasks; follow with short interviews about trust, missing information, and current workarounds.

## Tasks

1. Identify which jobs changed and which schedule version is current.
2. Explain why the proposal changed the sequence/resource.
3. Identify due-date, setup, and constraint impacts.
4. Decide whether to apply, adjust, or defer and explain why.
5. Respond to stale-input and no-feasible-proposal scenarios.
6. Explain how the rest of the shift would know which lineup to follow.

## What to observe

- Task completion and errors without facilitator help.
- Whether users can correctly explain the proposal’s rationale and key trade-off.
- Information users seek before deciding and where they hesitate.
- Whether stale-data and no-feasible states lead to safe next actions.
- Confidence, trust, and reasons for rejection, editing, or deferral.

Do not interpret a small moderated sample as proof of business impact. Use the findings to revise the workflow and decide what to instrument in a pilot.

## Prototype exit criteria

Move to a build-ready specification only when schedulers understand the comparison, can identify material impacts, and can tell whether a proposal is current and applied; open safety, permissions, and data questions are documented; and Engineering confirms the proposed behavior is feasible. If users need multiple ranked options or different explanations, revise the scope before development.

