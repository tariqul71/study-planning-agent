# User Stories

## US-01 Generate a weekly study plan

As a student, I want the agent to generate a 7-day plan from my assignments, so that I can focus on the most urgent and important work first.

### Acceptance criteria

AC-01 Given the student has entered three assignments with valid deadlines, When the student generates a weekly plan, Then all three assignments appear in the 7-day plan.

AC-02 Given two assignments have different deadlines, When the plan is generated, Then the system shows a visible reason for the suggested ordering.

AC-03 Given one assignment has no deadline, When the student requests a plan, Then the agent asks for the missing deadline instead of inventing one.

Related requirements: FR-02, FR-04, NFR-03, AG-01

## US-02 Explain why a task was scheduled early

As a student, I want to see why a task was scheduled early, so that I can judge whether the suggestion makes sense.

### Acceptance criteria

AC-01 Given a generated 7-day plan, When the student reviews the plan, Then the system shows a visible reason for the suggested order of tasks.

AC-02 Given deadline, estimated effort and priority were entered, When the explanation is shown, Then the agent exposes which of those inputs influenced the plan.

AC-03 Given the agent produces a suggestion, When the explanation is shown, Then the interface distinguishes that suggestion from facts the student entered, and the agent does not claim that an instructor approved the plan.

Related requirements: FR-04, AG-04, NFR-03, AG-02

## US-03 Regenerate the plan after a change

As a student, I want to regenerate the plan after changing a deadline, so that the plan reflects current information.

### Acceptance criteria

AC-01 Given a plan already exists, When the student changes an assignment deadline and regenerates the plan, Then the new plan uses the updated deadline.

AC-02 Given one changed assignment has no deadline, When the student requests regeneration, Then the agent asks for the missing deadline instead of inventing one.

AC-03 Given an external service fails during regeneration, When the failure is reported, Then the entered assignments are not deleted.

Related requirements: FR-03, AG-01, NFR-04

## US-04 Limit external integration permissions

As an IT administrator, I want external integrations to use minimum permissions, so that unnecessary account access is avoided.

### Acceptance criteria

AC-01 Given calendar access is enabled, When the agent needs availability, Then it may read permitted calendar availability and does not request write permission by default.

AC-02 Given a calendar change would be written, When the student has not confirmed that write, Then the system does not modify the external calendar.

AC-03 Given an external-service call fails, When the failure is reported, Then task data entered by the student is preserved.

Related requirements: NFR-02, AG-03, NFR-04
