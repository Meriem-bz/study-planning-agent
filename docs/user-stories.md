# User Stories

## US-01 Generate a weekly study plan

As a student, I want the agent to generate a 7-day plan from my assignments, so that I can focus on the most urgent and important work first.

### Acceptance criteria

- AC-01 Given the student has entered three assignments with valid deadlines, When the student generates a weekly plan, Then all three assignments appear in the 7-day plan.
- AC-02 Given two assignments have different deadlines, When the plan is generated, Then the system shows a visible reason for the suggested ordering.
- AC-03 Given one assignment has no deadline, When the student requests a plan, Then the agent asks for the missing deadline instead of inventing one.

Related requirements: FR-02, FR-04, NFR-03, AG-01

## US-02 Understand why a task is scheduled early

As a student, I want to see why a task was scheduled early, so that I can judge whether the suggestion makes sense.

### Acceptance criteria

- AC-04 Given a plan has been generated, When the student opens the plan, Then each task shows the reason for its position in the order.
- AC-05 Given the plan used a deadline and a priority to order tasks, When the student views the explanation, Then both the deadline and the priority are shown as factors.
- AC-06 Given the explanation is displayed, When the student reads it, Then user-provided facts are clearly separated from agent-generated suggestions.

Related requirements: FR-04, NFR-03, AG-04

## US-03 Regenerate the plan after a change

As a student, I want to regenerate the plan after changing a deadline, so that the plan reflects current information.

### Acceptance criteria

- AC-07 Given a plan already exists, When the student changes an assignment deadline and regenerates the plan, Then the new plan uses the updated deadline.
- AC-08 Given the student regenerates the plan, When the new plan is displayed, Then no assignment entered earlier is lost.
- AC-09 Given the student changes a deadline to an empty value, When the student regenerates the plan, Then the agent asks for the missing deadline instead of inventing one.

Related requirements: FR-01, FR-03, AG-01

## US-04 Limit external permissions

As an IT administrator, I want external integrations to use minimum permissions, so that unnecessary account access is avoided.

### Acceptance criteria

- AC-10 Given calendar access is enabled, When the agent connects to the calendar, Then it requests only the permission needed to read availability.
- AC-11 Given the agent suggests a change to the calendar, When the student has not confirmed it, Then the calendar is not modified.
- AC-12 Given the calendar service is unavailable, When the student requests a plan, Then the system reports the failure and keeps all entered assignments.

Related requirements: NFR-02, NFR-04, AG-03