# 1. Git workflow guidelines

Our projects will implement `agis`'s Git standards, defined in [this brief document](https://github.com/agis/git-style-guide/tree/3636597136ca32412382e1885ec46adb538ec7dc#readme).

- [1. Git workflow guidelines](#1-git-workflow-guidelines)
  - [1. How changes are made](#1-how-changes-are-made)
    - [1.1. The issue is created](#11-the-issue-is-created)
    - [1.2. The issue gets assigned to a contributor](#12-the-issue-gets-assigned-to-a-contributor)
    - [1.3. The issue gets resolved](#13-the-issue-gets-resolved)
  - [2. Branching](#2-branching)
  - [3. Issuing](#3-issuing)
    - [3.1. Bug reports](#31-bug-reports)
    - [3.2. Feature requests](#32-feature-requests)
    - [3.3. Enhancement](#33-enhancement)
  - [4. Pull requests](#4-pull-requests)
  - [5. Merging](#5-merging)
  - [6. Committing](#6-committing)
  - [7. Releases](#7-releases)
    - [7.1. Release notes](#71-release-notes)
    - [7.2. Hotfixes](#72-hotfixes)

## 1. How changes are made

### 1.1. The issue is created

A change starts when an issue with the details of the change is added to [the main project's GitHub repository](https://github.com/EthicApp-Development/ethicapp-main). There are two ways an issue is officially created:

- An issue is created by a contributor and then gets approved by a maintainer, for being addressed in the project.
- Directly created by a maintainer, from a user story that needs to be attended, or from a noticed bug.

For both cases, the maintainer has to ensure the issue has all the relevant information for the change, and it is labeled properly.

### 1.2. The issue gets assigned to a contributor

The maintainer coordinates the assignation of issues for each contributor. However, you can ask them to be assigned to a particular issue you would like to start working on. Once someone is assigned to an issue, a new branch is created to work on it, named with the format:

```txt
issue-NUMBER-TYPE
```

Where `NUMBER` is the issue number, and `TYPE` is the kind of issue: whether `bug`, `feature` (for new feature) or `enhancement`. For example, `"issue-47-feature"`.

This branch is created from the branch the issue refers to (e.g. from `overhaul-2122`, `unstable`, etc.). More details at [section 3](#3-issuing).

### 1.3. The issue gets resolved

After the contributor performs the changes to fulfill the requirements for the issue, at its branch, they raise a **pull request**, for merging the changes in the original branch. The maintainer performs code reviewing and QA, and once the pull request gets resolved, the changes are merged in the branch by the maintainer, closing the issue.

## 2. Branching

The branch for *EthicApp 2.0* is named `overhaul-2122`. The naming format for branches is declared at [section 1.2](#12-the-issue-gets-assigned-to-a-contributor).

## 3. Issuing

This section explain how and when to create issues in the [EthicApp's GitHub project repository](https://github.com/EthicApp-Development/ethicapp-main). The language of all issues will be **SPANISH**, unlike the rest of all documentation and code. This will make confusions less likely and will make it easier to post a bug report or other kind of issues for local contributors, as was started and will continue development on spanish-speaker universities (at Chile).

The format for issue names is `[BRANCH_NAME] ISSUE_TITLE`, for instance, *"[overhaul-2122] Error al cargar panel de control de profesor durante evaluación (HTTP 504 Gateway Timeout)"*. Only specific issues must be created, not general or vague issues, such as, for example, *"Actualizar frontend"*. Besides, there are 3 types of issues: bug report, feature request and enhancement, detailed below.

Note: have in mind that [our Discord server](https://discord.gg/w3MD6eX2Cx) will be used for general code discussions and questions, as explained on [section 1.2](./../CONTRIBUTING.md#12-discord) at the CONTRIBUTING file.

### 3.1. Bug reports

> A bug is a demonstrable problem that is caused by the code in the repository. Good bug reports are extremely helpful – thank you!
>
> — [Nicolas Gallagher](https://github.com/necolas/issue-guidelines/blob/2f69c9092efb4bae76592ae2eccdcb045bb333ca/CONTRIBUTING.md)

Before submitting a bug report, please search in the existing issues, as someone else could have reported the problem already. Once you have decided to submit a report, go to [issues](https://github.com/EthicApp-Development/ethicapp-main/issues) and hit the "New issue" button. Then, select click "*Reporte de error*" and enter the required information on that template.

<!-- TODO: example with screenshot -->

### 3.2. Feature requests

For posting a request for a new feature in the platform, first search in the existing issues and make sure nobody as already asked for such feature. For creating a new feature request, similarly to [when submitting a bug report](#31-bug-reports), select "*Nueva característica*" when creating the issue and fill the required fields.

<!-- TODO: example with screenshot -->

### 3.3. Enhancement

When you believe a change or enhancement is needed to an existing component of the project, you must create an issue from the template named *Mejora*.

<!-- TODO: example with screenshot -->

## 4. Pull requests

When attempting to close an issue, a pull request must be created to merge the issue branch with the finished job, into the target branch (e.g. `overhaul`, `develop`). The pull request must be titled `[TARGET_BRANCH_NAME] Issue #ISSUE_NUMBER: [MEANINGFUL_TITLE]` (e.g. `[overhaul-2122] Issue #26: error 404 when setting teacher question title larger than 128 chars`), and the body must include an explanation of the changes performed. The PR body must be in **SPANISH**, as it will be easier to discuss.

Then, a maintainer will assign a reviewer for your pull request, and once then code discussion between you and the reviewer gets resolved, the pull request will be approved and the maintainer will merge the changes finally to the target branch.

## 5. Merging

When a maintainer pretends to merge, always use the **not fast-forward** flag, so as to always create a merge commit and have a more clear change history:

```shell
git merge --no-ff [...]
```

[GitHub Desktop](https://desktop.github.com/) (also available for Linux) can be a very helpful tool for handling merges, as it may be more intuitive than `vscode`.

## 6. Committing

Commit messages must match the following format:

```text
[COMPONENT_NAME] MEANINGFUL_TITLE (#ISSUE_NUMBER)

ADDITIONAL_DESCRIPTION
```

Where:

- `COMPONENT_NAME` will depend on the nature of the commit, and has to be the affected component or module by the commit (e.g. controller name, view template name). There will be some specific cases in which `COMPONENT_NAME` would not apply (e.g. when a important dependency is updated at `package.json`, etc.), but for most of cases, it must be included.
- `MEANINGFUL_TITLE` is a brief and concise title of the changes of the commit.
- `ISSUE_NUMBER` is the repository's issue number the commit refers to.
- `ADDITIONAL_DESCRIPTION`: optional, and useful for when desiring to provide a more detailed explanation of the change, or desiring to list more than one necessary change in the commit. For this last case, list them as a markdown list, as the example below shows.

Keep in mind that the first line of the commit message **must not exceed 50 characters long**, so avoid large titles, add explanation in further lines when needed. This is important, so as to be able to view the issue number from GitHub's commit history. Also, note that there is a blank line between the commit title and the body.

Example:

```text
[RoleController] Fixed broken URL for student profiles (#40)

- Small typo fix at SomeControllerMethod causing bad href.
```

Finally, be prudent with the size of your commits, i.e., try to avoid commits with a single change in a single file, and also avoid commits with huge changes in multiple files.

## 7. Releases

EthicApp (after version 2.0) will regularly publish new versions through [GitHub's releases](https://docs.github.com/en/repositories/releasing-projects-on-github/viewing-your-repositorys-releases-and-tags). The naming for versions will follow the [SemVer](https://semver.org/) standard.

A new version (new release) is defined as a relevant change from the previous version, not including small changes or "patches". In other words (and following SemVer), a release will be named with the following level of granularity:

```text
MAJOR.MINOR
```

Thus by skipping the `PATCH` identifier of SemVer, due to the nature of EthicApp as a web application (except for the case of a *hotfix*, see section [7.2](#72-hotfixes)).

Every marge to the `master` branch of the main repository should have stable and significant changes, and thus conform a new *release*. When this is performed, it must be labeled in the previously declared format, and it must be published along with *release notes*, as defined in the following section, using GitHub's built-in releases (within the main repository).

### 7.1. Release notes

Note that GitHub releases support Markdown. The release notes must follow the following format, and must be in Spanish, so that both technical and non-technical users can easily identify changes between versions:

```markdown
## MAJOR.MINOR
### Novedades principales
[List of visible changes very oriented to the non-technical user, e.g. members of the academic community]

### Aspectos técnicos
[A more detailed list including **relevant** technical changes, e.g. relevant issues solved, refactorings, architectural changes, etc.]
```

### 7.2. Hotfixes

Only in the case of a hotfix (i.e. a necessary correction of an important bug of a previous version, after it was released), a new release should be published immediately and must have the versioning format:

```text
MAJOR.MINOR.PATCH
```
