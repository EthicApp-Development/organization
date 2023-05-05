# EthicApp

EthicApp is an open-source academic project designed to help higher education students (and teachers) in carrying through ethic discussions.

> EthicApp is a collaborative application to support students’ development of ethical discernment and moral reasoning. It is available as a web application that can be accessed by any device with a capable web browser, including desktop computers, smart phones, or tablets. EthicApp works in face-to-face or distributed settings, synchronously or asynchronously. [[1]](#1)

This repository contains information of the [`EthicApp-Development` GitHub organization](https://github.com/EthicApp-Development) exclusively for developing the EthicApp project, which main repository is [`ethicapp-main`](https://github.com/EthicApp-Development/ethicapp-main). For a much more detailed and technical explanation of the project, consider reviewing the paper *Automatic Content Analysis of Student Moral Discourse in a Collaborative Learning Activity* (see [references section](#42-references)).

## 1. Vision and goals

The core goal of the EthicApp project is to help students to fullfil ethic competences required for their higher education careers.

EthicApp is a tool designed to be used in a formal ethics course in higher education institutions, both synchronously or asynchronously. It brings support of deliberation (identification and decision on a dilemma) by providing automation on the creation of these activities trough its web platform, allowing teachers to create and share templates of instructions of activities. These templates can then used to design questions based on an ethic case and students can answer anonymously, encouraging honesty, and these templates can be shared among teachers as well. When an activity is complete, EthicApp collects data for the teacher so they can have insights of the results and be conscious of the ethical choices of the students and thus helps them deciding educational strategies, deciding a solution for the ethical conflict in study and providing feedback to students.

## 2. Brief history

EthicApp was started at [Universidad de Chile](https://uchile.cl/) in 2017 by a research team, as a project oriented on supporting abilities of the XXI century for individuals, acting as a complementary service for their professional profile (curriculum). This project eventually was turned into a complementary academic platform for formal courses of ethics in high education institutions. Since 2019, EthicApp is a collaborative project between [Universidad de Chile](https://uchile.cl/) and [Universidad de los Andes](https://uandes.cl/) towards this fully academic vision.

Currently, this project is being successfully implemented in a small amount of universities at a local scope (national, chilean). In a close future, as organization, we would like to facilitate the adoption of EthicApp in other institutions, increasing the number of users and giving the first steps in becoming a significant contribution to ethical education.

## 3. Contributing to this project

If you intend to contribute, please review [this document](./CONTRIBUTING.md). You may want to check [appendix 4.1](#41-languages-for-this-project) as well.

## 4. Appendixes

### 4.1. Languages for this project

As the industry standard language for software developing is english, but the project is developed in a spanish-speaker country, these two languages will be used in different contexts, which are mentioned over the documentation files. As this can be confusing, the following table shows clearly which language must be used depending on the setting.

| Context                                                   | Language                    |
| --------------------------------------------------------- | --------------------------- |
| Source code files (naming, commenting)                    | :large_blue_circle: English |
| Documentation files (markdown)                            | :large_blue_circle: English |
| Git commit messages                                       | :large_blue_circle: English |
| Branch names                                              | :large_blue_circle: English |
| GitHub pull requests                                      | :red_circle: Spanish        |
| GitHub issues                                             | :red_circle: Spanish        |
| Communication on [Discord](https://discord.gg/w3MD6eX2Cx) | :red_circle: Spanish        |

### 4.2. References

<!-- Using IEE standard with hardcoded HTML IDs so as to properly reference items -->

<a id="1" href="https://www.researchgate.net/publication/354112860_Automatic_Content_Analysis_of_Student_Moral_Discourse_in_a_Collaborative_Learning_Activity">[1]</a>
C. Alvarez, G. Zurita, A. Carvallo, P. Ramírez, E. Bravo, and N. Baloian, “Automatic Content Analysis of Student Moral Discourse in a Collaborative Learning Activity,” Collaboration Technologies and Social Computing, 2021, doi: https://doi.org/10.1007/978-3-030-85071-5_1.

<a id="2" href="https://www.tutorialspoint.com/software_testing_dictionary/known_issues.htm">[2]</a>
“Known Issues,” TutorialsPoint.

### 4.3. Acknowledgements

- The structure for [EthicApp's JavaScript guidelines document](./Guidelines/JavaScript.md) was highly inspired in [Visual Studio Code's coding guidelines](https://github.com/microsoft/vscode/wiki/Coding-Guidelines).
- The issues guidelines were inspired from [Nicolas Gallagher's `issue-guidelines` project](https://github.com/necolas/issue-guidelines/blob/master/CONTRIBUTING.md).
- The GitHub issue templates from [Microsoft's PowerToys](https://github.com/microsoft/PowerToys/tree/main/.github/ISSUE_TEMPLATE) and [rubrikinc](https://github.com/rubrikinc/template/blob/50ed3c71920695810329ca75b8727a3f56083417/.github/ISSUE_TEMPLATE/enhancement-request.md) were used as reference to [EthicApp's issue templates](https://github.com/EthicApp-Development/ethicapp-main/tree/master/.github/ISSUE_TEMPLATE) (at the main project repository).
- The structure for channels and categories of [our development Discord server](https://discord.gg/w3MD6eX2Cx) was inspired in [OBS Studio's](https://obsproject.com/discord).
