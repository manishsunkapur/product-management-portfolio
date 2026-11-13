# 07 · User Stories and Acceptance Criteria

## Epic

**Help a production scheduler recover an active lineup after a resource disruption with an understandable and feasible proposal.**

The following stories are provisional. Refine them after discovery, current-product review, design, and technical feasibility work.

## P0 · Understand the event and the proposal

### US-01 · Confirm the event inputs

**As a production scheduler,** I want to see the affected resource, event status, and freshness of the production data, **so that** I can judge whether the recovery proposal is based on current inputs.

**Acceptance criteria**

- Show the resource, event time, current status, and last-updated time for relevant inputs.
- Distinguish confirmed data from an estimate or unavailable value.
- If an event is cleared, duplicated, stale, or conflicts with a newer event, do not present it as an unqualified current condition.
- Preserve the last confirmed schedule while an event is unresolved.

### US-02 · Compare current and proposed schedules

**As a production scheduler,** I want to see which jobs and resources change between the current and proposed lineup, **so that** I can understand the operational impact before acting.

**Acceptance criteria**

- Show the current and proposed time/resource for each affected job.
- Highlight additions, removals, sequence changes, and unchanged jobs in scope.
- Make the proposal version and calculation time visible.
- Do not imply a proposed schedule has been applied until the action succeeds.

### US-03 · Understand the trade-offs

**As a production scheduler,** I want to see delivery risk, setup impact, downstream constraints, and the reason for the proposed sequence, **so that** I can determine whether it fits plant priorities.

**Acceptance criteria**

- Show customer-defined due-date risk and relevant time buffers where the data supports them.
- Show expected additional setup/changeover impact and any unsatisfied hard constraints.
- Explain the proposal’s main reason using understandable operational terms.
- Label estimated or missing impacts rather than presenting them as facts.

## P1 · Make and communicate the decision

### US-04 · Apply, adjust, or defer

**As an authorized scheduler,** I want to apply, adjust, or defer a proposal, **so that** I can retain control of the recovery decision.

**Acceptance criteria**

- Only users with the appropriate role can apply a schedule change.
- Confirm the proposal is still current before applying it; require refresh if relevant inputs changed.
- On success, show the new schedule version and decision status.
- Record the user, action, time, and proposal version where customer workflow requires an audit trail.
- On failure, keep the prior confirmed schedule and explain what the user can do next.

### US-05 · Handle no feasible proposal

**As a production scheduler,** I want the system to tell me when it cannot create a feasible recovery, **so that** I can take manual action without trusting an invalid schedule.

**Acceptance criteria**

- Clearly state that no feasible proposal is available.
- Identify the blocking constraint(s) to the extent permitted and useful.
- Keep the existing schedule visible and unchanged.
- Provide an appropriate next step, such as correcting inputs or continuing with manual planning.

### US-06 · Keep the floor on the current schedule

**As a shift supervisor,** I want to know which schedule version is current after a recovery decision, **so that** the floor can follow one clear lineup.

**Acceptance criteria**

- Show the applied/current version and when it took effect.
- Make schedule status available through the workflow or communication channel confirmed in discovery.
- Do not assume push notifications, text messages, or a specific hardware display until implementation and customer workflows are understood.

## Cross-cutting analytics requirement

Record the minimum events needed to measure proposal generation, review, action, failure, and recovery time. Avoid collecting unnecessary personal or customer-sensitive data.

## Definition of ready

A story is ready when its user need and outcome are evidenced, behavior and edge cases are clear, dependencies and data assumptions are documented, design is reviewable, analytics is specified, and Product/Engineering/QA agree on acceptance criteria.

## Example · Given / When / Then

**Given** an active schedule and a recovery proposal whose inputs are still current, **when** an authorized scheduler applies the proposal, **then** the system confirms the new schedule version and records the decision. If validation or the update fails, the previous confirmed schedule remains current and the user sees a clear recovery action.

## Framework fit

- Use **INVEST** as a story-quality checklist: independent where practical, negotiable, valuable, estimable, small, and testable. It is a guide, not a reason to split work artificially.
- Use **Given / When / Then** to make examples and acceptance behavior clear, including failure and permission cases.
- Acceptance criteria define observable behavior; QA test design and technical design still require collaboration with Engineering and QA.
