# Ways of working

This document contains a set of recommendations on how to work on the i-on projects

## Recommendations

* Think.

* Use this document's git history to track recommendations changes.

* Documentation should be stored in the project repository (e.g. under a `docs` folder).
  * Prefer text-based formats for the documentation source (e.g. markdown), namely formats that are automatically rendered by GitHub.
  * Only use a wiki page for simple content that doesn't need peer review (e.g. the weekly calendar).
  * After _brain storming_ sessions, take time to write out the design conclusions and their rationale.

* If it isn't in git, then it does not exist (with very few exceptions, namely for private content).

* Create GitHub issues for all activities being done, including: analysis, documentation, development of new features, corrections. 
  * Organize those issues on the repository's _project board_.
  * Use the issues' description to document the task being done (or link to the external documentation).
  * As an alternative, use the PR as the issue.
  * Use the `PS` label for all the tasks that are related to "Projecto e Seminário" deliverables (e.g. reports).

*  All work should be done on short-lived branches.
    * Naming scheme: `[feature|fix|docs|spike]/gh-nnn-description-using-kebab-case`, where `nnn` is the number of the issue describing the task.
    * The merge of these branches into `dev` should use [pull requests (PR)](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests).
    * The PR author decides who are the reviewers, taking into consideration information or requirements in the issue.
    * See [Google Code Review practices](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests) for recommendations on how to do a PR review.
    * Ensure timely review of the assigned PRs.
    * When applicable, a PR should only be accepted if it passed CI builds.

* Keep the repository tidy. Namely, before a commit double check what is staged or configured to be included on it.

* Do not rewrite the git history of publicly committed branches. namely `master`.

* Each project's main repository should have a GitHub project (e.g. [https://github.com/i-on-project/core/projects/2])
  * The project has the following columns
    * `To Define` - Task that might need to be done, however isn't yet fully defined or agreed upon.
    * `To Do` - Task that needs to be done.
    * `Doing` - Task that is beeing done.
    * `Review` - Task that is pending review. A PR should probably exist for it.
    * `Done` - Task is done.
    * `Rejected` - Task will not be done.

* Each project should have one milestone per week
  * Uses the following naming convention `Wnn-2021`, where the `nn` is the week number.
  * If a weekly milestone is too fine grained, then we can have a fortnighly one. The numbering should still be weekly, so we would have `W01-2021`, followed by `W03-2021`.
  * Each task should have an associated milestone, namely if they are on the project board and already out of the `To Define` phase.


