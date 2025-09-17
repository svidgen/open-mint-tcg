# Open Mint TCG RFC Process

## Overview

Changes to Open Mint TCG (the game) should occur primarily through RFCs (Requests for Comments) with the notable exception being *bug fixes*. An RFC is a document that describes the impetus, intent, analysis, and detailed design of a change to the game.

The reasons we use this specific RFC process:

1. **To facilitate collaborative decision making.**<br /> RFCs will be created through PRs which are inherently open to public commenting. The RFCs documents themselves can also collaborative, having multiple authors over time until they're *ready*.
2. **To keep a record of decisions *versioned alongside the implementation*.**<br /> This will hopefully help us avoid [Chesterton's Fences](https://en.wikipedia.org/wiki/G._K._Chesterton#Chesterton's_fence) down the line. There should ideally be no question as to when any given rule came into being and why that rule was created.
3. **To bless, solicit, and coordinate contributions.**<br /> And existing, unimplemented RFC is a clear-cut blessing that contributions to implement the RFC are welcome. Contributions *outside* of those indicated by an RFC are likely to be rejected outright.

If the process fails to meet these goals, [start a conversation](https://github.com/svidgen/open-mint-tcg/issues) or submit a PR to help improve the process.

## RFC States

Each RFC will have a `State` field at the top of its markdown file. The possible states are as follows:

| State | Meaning |
| -- | -- |
| **Draft** | A work-in-progress set of proposed changes to the game. In this state, an RFC is expected to contain a *explicit* list of unresolved questions and/or underdeveloped sections. |
| **Accepted** | A change to the game that has been approved for implementation. At this stage, edits may still be accepted during implementation to reconcile any oversights. |
| **Live** | Fully implemented in conformance tests and incorporated into the spec. Officially part of the game. |
| **Withdrawn** | An RFC that is no longer intended as binding on the game. Only RFCs in the **Draft** or **Accepted** state that are found to be flawed beyond repair or which have been overwhelmingly protested can become **Withdrawn**. Once an RFC has gone "Live", it can only be reversed by being **Superseded** with a new RFC. |
| **Superseded** | When an RFC should be ignored in favor of another RFC that potentially even reverses it. |

RFCs in each of these states may live in the repository as *committed code*. A PR approval is not synonymous with a PR in any particular state.

## Recommended Workflow

1. **Propose.**<br /> Create an [issue](https://github.com/svidgen/open-mint-tcg/issues) to proposing the RFC at a high level. At this stage, try to gain a sense for whether the community and maintainers see merit in the idea and what questions they expect the RFC would need to address. Try to get high level direction on key points here before proceeding. If you're uncomfortable creating and babysitting the actual RFC, feel free to ask for volunteers to own the RFC.
2. **Pull Request.**<br /> Submit a new RFC as a markdown file in a PR. Use [the template](./rfc/TEMPLATE.md). Include as much detail as you're able. So long as an RFC is in a **Draft** state, it should include a list of **Open Items** indicating the aspects of the RFC are *intentionally* incomplete. (Unresolved questions or underdeveloped sections.)
3. **Incorporate Feedback.**<br /> Respond to PR questions and concerns. Iterate on the PR until it is approved for merging &mdash; generally as a **Draft** to start. Reviewers will generally require that you enumerate unsettled items in the Open Items section.
4. **More Pull Requests.**<br /> Submit PRs and/or review PRs against the RFC until all open items are addressed. Simultaneous to removing the last Open Item, flip the status to **Accepted**.
5. **Feature Branch.**<br /> Maintainers will create a feature branch for implementation work.
6. **Implement.**<br /> Create PRs against the feature branch to implement the RFC. This is not necessarily the RFC author's responsibility, though the RFC author is encouraged to. PRs are needed to do the following:
	1. Update [the spec](./spec/) to align with the RFC.
	2. Add functionality to [the library](packages/lib/)
	3. Updated [conformance tests](./packages/conformance-tests/)
	4. Update the status to **Live** in the feature branch.
7. **Release.**<br /> Create a PR from the feature branch to `main`. Once approved and merged, the feature branch will be deleted. At this point, maintainers and/or automation will take over.

## RFC Formatting

- Use [the template](./rfc/TEMPLATE.md).
- Name the file `rfc/NNNN-short-title.md`, where:
	- `NNNN` is a four-digit number, assigned sequentially (e.g., `0001`, `0002`, ...).
	- `short-title` is a brief, lowercase, hyphen-separated summary of the RFC’s subject.
	- Example: `0001-card-generation.md`
- The filename should not change after the RFC is submitted.

## Tracking

- All RFCs must be listed in `rfc/README.md` with their current state.
- State must also be maintained in the RFC file.

## Tests

- Every **Live** RFC should have corresponding tests in `packages/conformance-tests` to validate correct implementations.
- An **Accepted** RFC should have specification tests in `packages/spec-tests` to validate all of the less obvious assumptions and claims in the RFC itself.
- Similarly, the assumptions of the "live" specification itself should be validated with tests.

## Questions?

Open an [issue](https://github.com/svidgen/open-mint-tcg/issues) in the repository.
