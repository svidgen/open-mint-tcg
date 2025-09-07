# Open Mint TCG RFC Process

## Overview

The RFC (Request for Comments) process is how we propose, discuss, and adopt changes to the Open Mint TCG project. This includes new features, rule changes, and process updates.

## RFC States


Each RFC has a `State:` field at the top of its markdown file. The possible states are:

- **Draft**: Under discussion, not yet accepted.
- **Accepted**: Approved and merged, but not yet implemented in conformance tests or the spec.
- **Implemented**: Implementation and conformance tests are in progress or completed, but not yet fully integrated into the spec.
- **Live**: Fully implemented in conformance tests and incorporated into the spec. Officially part of the project.
- **Rejected/Withdrawn**: Not pursued.

## Workflow

1. **Draft**: Submit a new RFC as a markdown file in a PR. Discuss and revise.
2. **Accepted**: Once consensus is reached, merge the RFC with `State: Accepted (Pending Implementation)`.
3. **Live**: A follow-up PR must implement conformance tests and update the spec, then set the RFC's state to `Live`.
4. **Rejected/Withdrawn**: If not pursued, mark as such and close the PR.


## RFC Filenames

- RFC filenames must be unique and use the format: `NNNN-short-title.md`, where:
	- `NNNN` is a four-digit number, assigned sequentially (e.g., `0001`, `0002`, ...).
	- `short-title` is a brief, lowercase, hyphen-separated summary of the RFC’s subject.
- Example: `0001-card-trading-rules.md`
- The filename should not change after the RFC is submitted.
- Add a line to `rfcs/index.md` for each RFC, including its filename, title, state, author, and created date.

## Tracking

- All RFCs are listed in `rfcs/index.md` with their current state.
- Each RFC file must have a `State:` field at the top.

## Conformance Tests

- Every "Live" RFC must have corresponding tests in `conformance-tests/`.
- The package `packages/rfc-test-utils` provides helpers for writing these tests.

## Example RFC Header

```
---
Title: Example Feature
State: Draft
Author: @username
Created: 2025-09-07
---
```

## Questions?

Open an issue or discussion in the repository.
