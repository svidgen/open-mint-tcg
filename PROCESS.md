# Open Mint TCG RFC Process

## Overview

The RFC (Request for Comments) process is how we propose, discuss, and adopt changes to Open Mint TCG.

## RFC States

Each RFC has a `State:` field at the top of its markdown file. The possible states are:

- **Draft**: Under discussion, not yet accepted.
- **Accepted**: Approved and merged, but not yet implemented in conformance tests or the spec.
- **Live**: Fully implemented in conformance tests and incorporated into the spec. Officially part of the project.
- **Withdrawn**: For when an RFC is found to be flawed or unwanted after drafting post-draft. (This is only valid prior to being "Live". Once an RFC is "Live", it should be "Superseded" with another RFC.)
- **Superseded**: When an RFC should be ignored in favor of another RFC that potentially even reverses it.

## Recommended Workflow

If you are confident in your change or don't mind having an unwanted PR abruptly closed, feel free to jump straight to submitting a PR. Otherwise, we suggest following these steps.

1. **Propose**: Create an [issue](https://github.com/svidgen/open-mint-tcg/issues) to propose an change and again *early* feedback.
2. **Draft**: Submit a new RFC as a markdown file in a PR. Discuss and revise.
3. **Merge**: Once consensus is reached, merge the RFC with `State: Accepted`.
4. **Implement**: A follow-up PR must implement the RFC. A PR is generally required that:
	1. Updates [the spec](./spec/) to with with the RFC.
	1. Adds functionality [The library](packages/lib/)
	2. [Conformance tests](./packages/conformance-tests/)

## RFC Filenames

- RFC filenames must be unique and use the format: `NNNN-short-title.md`, where:
	- `NNNN` is a four-digit number, assigned sequentially (e.g., `0001`, `0002`, ...).
	- `short-title` is a brief, lowercase, hyphen-separated summary of the RFC’s subject.
- Example: `0001-card-trading-rules.md`
- The filename should not change after the RFC is submitted.
- Add a line to `rfcs/README.md` for each RFC, including its filename, title, state, author, and created date.

## Tracking

- All RFCs are listed in `rfcs/README.md` with their current state.
- Each RFC file must have a `State:` field at the top.

## Tests

- Every "Live" RFC must have corresponding tests in `packages/conformance-tests` to validate correct implementations.
- Every RFC should *likely* have specification tests in `packages/spec-tests` to validate the assumptions of the RFC itself.
- Similarly, the assumptions of the "live" specification itself should be validated with tests.

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
