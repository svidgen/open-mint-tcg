# Open Mint TCG RFC Process

## Overview

Changes to Open Mint TCG (the game) should generally occur through RFCs (Requests for Comments). An RFC is a document that captures the impetus, reasoning, and details of a change.

## RFC States

Each RFC will have a `State` field at the top of its markdown file. The possible states are as follows:

| State | Meaning |
| -- | -- |
| **Draft** | A rough, proposed change to the game. In this state, an RFC is expected |
| **Accepted** | A change to that game that has largely been approved, pending successful implementation. At this stage, edits may occur to reconcile oversights in the RFC with newly discovered information. (Or conflicts with reality.)  |
| **Live** | Fully implemented in conformance tests and incorporated into the spec. Officially part of the game. |
| **Withdrawn** | An RFC that is no longer intended as binding on the game. Only RFCs in the **Draft** or **Accepted** state that are found to be flawed beyond repair or overwhelmingly protested can become **Withdrawn**. Once an RFC has gone "Live", it can only be reversed by being **Superseded** with a new RFC. |
| **Superseded** | When an RFC should be ignored in favor of another RFC that potentially even reverses it. |

RFCs in each of these states may live in the repository as *committed code*. A PR approval is not synonymous with a PR in any particular state.

## Recommended Workflow

These steps are recommended. If you don't mind being ignored or told "no" abruptly and having your PR closed without discussion, you're more than welcome to take a stab at skipping steps.

1. **Propose**: Create an [issue](https://github.com/svidgen/open-mint-tcg/issues) to proposing the RFC at a high level. At this stage, try to gain a sense for whether the community and maintainers see merit in the idea and what questions they expect the RFC would need to address. Try to get high level direction on key points here before proceeding. If you're uncomfortable creating and babysitting the actual RFC, feel free to ask for volunteers to own the RFC.
2. **RFC PR**: Submit a new RFC as a markdown file in a PR. Use [the template](./rfc/TEMPLATE.md). Include as much detail as you're able. So long as an RFC is in a **Draft** state, it should include a list of **Open Items** indicating the aspects of the RFC are *intentionally* incomplete.
3. **Incorporate Feedback**: Respond to PR questions and concerns. Iterate on the PR until it is approved for merging &mdash; generally as a **Draft** to start. Reviewers will generally require that you enumerate unsettled items in the Open Items section.
4. **Iteratively PR**: Submit PRs and/or review PRs against the RFC until all open items are addressed. Simultaneous to removing the last Open Item, flip the status to **Accepted**.
5. **Wait for Feature Branch**: Maintainers will create a feature branch for implementation work.
6. **Implement**: Create PRs against the assigned feature branch to implement the RFC. This is no one's sole responsibility. PRs are required to:
	1. Update [the spec](./spec/) to align with the RFC.
	2. Add functionality to [the library](packages/lib/)
	3. Updated [conformance tests](./packages/conformance-tests/)

## RFC Files

- RFC filenames must be unique and use the format: `NNNN-short-title.md`, where:
	- `NNNN` is a four-digit number, assigned sequentially (e.g., `0001`, `0002`, ...).
	- `short-title` is a brief, lowercase, hyphen-separated summary of the RFC’s subject.
- Example: `0001-card-trading-rules.md`
- The filename should not change after the RFC is submitted.
- Add a line to `rfc/README.md` for each RFC, including its filename, title, state, author, and created date.
- Use [the template](./rfc/TEMPLATE.md)

## Tracking

- All RFCs are listed in `rfc/README.md` with their current state.
- Each RFC file must have a `State:` field at the top.

## Tests

- Every "Live" RFC must have corresponding tests in `packages/conformance-tests` to validate correct implementations.
- Every RFC should *likely* have specification tests in `packages/spec-tests` to validate the assumptions of the RFC itself.
- Similarly, the assumptions of the "live" specification itself should be validated with tests.

## Questions?

Open an issue or discussion in the repository.
