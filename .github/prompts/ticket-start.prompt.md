---
mode: 'agent'
---

# Start working in a ticket

The ticket should have a description in 01-ticket-name.md. If not stop the process.

Notes for every step below:

- Include the timestamp (including seconds) when the planning started and finished. It will be used to show the total time invested on the ticket.
- Do not start the next phase until the user approves the current, suggest to review and continue with the next phase.
- Only modify the file (if exists) of the current phase.

## Phase 02: Planning

Create a new file named `02-planning.md` in the ticket directory. In this file, write a detailed implementation plan outlining the steps required to solve the ticket. Keep it simple and concise. The plan should include:

- A summary of the problem and goals
- A breakdown of tasks and subtasks
- Any assumptions or dependencies
- Estimated effort for each step

Ensure the plan is clear, actionable, and addresses all requirements described in 01-ticket-name.md.

## Phase 03: Implementation

Create a `03-implementation.md` to include any relevant details that happens during the implementation, keep it simple and concise.

Do not modify the ticket or the planning during the implementation.

## Phase 04: Summary

Create a `04-summary.md` file with the summary after the implementation

Do not modify the ticket, the planning or the implementation during the summary.

## Phase 05: Ship

Give the option to the user to commit the results with the Git MCP Server:

1. Create a branch based on the ticket name (folder name)
2. Commit the changes with a commit message which follow conventional commits and only title, no body
3. Push the branch
