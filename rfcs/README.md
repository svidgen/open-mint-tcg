# RFCs for Open Mint TCG

This directory contains Requests for Comments (RFCs) for the Open Mint Trading Card Game project.

## RFC Lifecycle

Each RFC is a markdown file describing a proposed change, feature, or process. RFCs move through the following states:

- **Draft**: The RFC is under discussion and not yet accepted.
- **Accepted (Pending Implementation)**: The RFC has been approved and merged, but is not yet implemented in conformance tests or the spec. (Also called "Pending", "Queued", or "Staged".)
- **Live**: The RFC is implemented in conformance tests and incorporated into the spec. It is now part of the official project.
- **Rejected/Withdrawn**: The RFC will not be pursued.

Each RFC should include a `State:` field at the top, e.g.:

```
State: Draft
```

## Process

1. **Draft**: Propose an RFC as a markdown file in a PR. Discuss and revise as needed.
2. **Accepted**: Once consensus is reached, the RFC is merged with `State: Accepted (Pending Implementation)`.
3. **Live**: A follow-up PR must implement conformance tests and update the spec, then set the RFC's state to `Live`.
4. **Rejected/Withdrawn**: If not pursued, mark as such and close the PR.

A list of RFCs and their states is maintained in `rfcs/index.md`.
