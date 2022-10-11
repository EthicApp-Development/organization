# 1. Git workflow guidelines

Our projects will implement `agis`'s Git standards, defined in [this brief document](https://github.com/agis/git-style-guide/tree/3636597136ca32412382e1885ec46adb538ec7dc#readme).

- [1. Git workflow guidelines](#1-git-workflow-guidelines)
  - [1. How changes are made](#1-how-changes-are-made)
    - [1.1. The issue is created](#11-the-issue-is-created)
    - [1.2. The issue gets assigned to a contributor](#12-the-issue-gets-assigned-to-a-contributor)
    - [1.3. The issue gets resolved](#13-the-issue-gets-resolved)
  - [2. Issuing](#2-issuing)
    - [2.1. Bug reports](#21-bug-reports)
    - [2.2. Feature requests](#22-feature-requests)
  - [3. Pull requests](#3-pull-requests)
  - [4. Merging](#4-merging)
  - [5. Committing](#5-committing)

## 1. How changes are made

### 1.1. The issue is created

A change starts when an issue with the details of the change is added to [the main project's GitHub repository](https://github.com/EthicApp-Development/ethicapp-main). There are two ways an issue is officially created:

- An issue is created by a contributor and then gets approved by a maintainer, for being addressed in the project.
- Directly created by a maintainer, from a user story that needs to be attended, or from a noticed bug.

For both cases, the maintainer has to ensure the issue has all the relevant information for the change, and it is labeled properly.

### 1.2. The issue gets assigned to a contributor

A contributor assigns themselves the issue, and starts working on it, by creating a new branch to work on it, named `issue-X`, where `X` is the issue number. This branch is created from the branch the issue refers to (more details in the next section).

### 1.3. The issue gets resolved

After the contributor performs the changes to fulfill the requirements for the issue, at its branch, they raise a pull request, for merging the changes in the original branch. The maintainer performs code reviewing and QA, and once the pull request gets resolved, the changes are merged in the branch by the maintainer, closing the issue.

## 2. Issuing

This section explain how and when to create issues in the [EthicApp's GitHub project repository](https://github.com/EthicApp-Development/ethicapp-main). The language of all issues will be **SPANISH**, unlike the rest of all documentation and code. This will make confusions less likely and will make it easier to post a bug report or other kind of issues for local contributors, as was started and will continue development on spanish-speaker universities (at Chile).

The format for issue names is `[BRANCH NAME] ISSUE TITLE`, for instance, *"[ethicapp-overhaul] Error al cargar panel de control de profesor durante evaluación (HTTP 504 Gateway Timeout)"*. Only specific issues must be created, not general or vague issues, such as, for example, *"Actualizar frontend"*. Besides, there are 3 types of issues, with are defined in this section as follows.

### 2.1. Bug reports

> A bug is a demonstrable problem that is caused by the code in the repository. Good bug reports are extremely helpful – thank you!
>
> — [Nicolas Gallagher](https://github.com/necolas/issue-guidelines/blob/2f69c9092efb4bae76592ae2eccdcb045bb333ca/CONTRIBUTING.md)

Before submitting a bug report, please search in the existing issues, as someone else could have reported the problem already. Once you have decided to submit a report, go to [issues](https://github.com/EthicApp-Development/ethicapp-main/issues) and hit the "New issue" button. Then, select click "*Reporte de error*" and enter the required information on that template.

<!-- TODO: example with screenshot -->

### 2.2. Feature requests

For posting a request for a new feature in the platform, first search in the existing issues and make sure nobody as already asked for such feature. For creating a new feature request, similarly to [when submitting a bug report](#21-bug-reports), select "*Nueva característica*" when creating the issue and fill the required fields.

<!-- TODO: example with screenshot -->

<!-- TODO: mention that, for questions and discussion, a Discord server will be used, in which contributors can join -->

## 3. Pull requests

When attempting to close an issue, a pull request must be created to merge the issue branch with the finished job, into the target branch (e.g. `overhaul`, `develop`). The pull request must be titled `[BRANCH_NAME] Closes #ISSUE_NUMBER: [MEANINGFUL_TITLE]` (e.g. `[overhaul] Closes #26: error 404 when setting teacher question title larger than 128 chars`), and the body must include an explanation of the technical changes performed. Both pull title and body must be in **ENGLISH**.

Then, a maintainer will review this pull request, and when then code discussion gets resolved, the pull request will be approved and the maintainer will merge the changes finally to the target branch.

## 4. Merging

When a maintainer pretends to merge, always use the **not fast-forward** flag, so as to always create a merge commit, and have a more clear change history:

```shell
git merge --no-ff [...]
```

[GitHub Desktop](https://desktop.github.com/) (also available for Linux) can be a very helpful tool for handling merges, as it may be more intuitive than `vscode`.

<!-- TODO: tutorial of how to perform a non-fast-forward merge on vscode IDE -->

## 5. Committing

Commit messages must match the following format:

```text
[COMPONENT_NAME] MEANINGFUL_TITLE (#ISSUE_NUMBER)

[ADDITIONAL_INFORMATION]
```

Where:

- `COMPONENT_NAME` will depend on the nature of the commit, and has to be the affected component by the commit (e.g. controller name, view template name). There will be some specific cases in which `COMPONENT_NAME` would not apply (e.g. when a important dependency is updated at `package.json`, etc.), but for most of cases, it must be included.
- `MEANINGFUL_TITLE` is a brief and concise title of the changes of the commit.
- `ISSUE_NUMBER` is the repository's issue number the commit refers to.
- `ADDITIONAL_INFORMATION`: optional, and useful for when desiring to provide a more detailed explanation of the change, or desiring to list more than one necessary change in the commit. For this last case, list them as a markdown list, as the example below shows.

Keep in mind that the first line of the commit message **must not exceed 50 characters long**, so avoid large titles, add explanation in further lines when needed. This is important, so as to be able to view the issue number from GitHub's commit history.

Example:

```text
[RoleController] Fixed broken URL for student profiles (#40)

- Small typo fix at SomeControllerMethod causing bad href.
```

<!-- TODO: diagram where all branches and their purpose are clear (e.g. explained distinction between main and overhaul), or should this be done only when the project is near-ready to be published? -->
