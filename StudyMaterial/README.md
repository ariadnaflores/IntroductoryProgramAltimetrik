# IntroductoryProgramAltimetrik

## Table of Contents

1. [Git](#git)
2. [Basic commands](#basic-commands)
3. [Branches](#branches)
4. [Merging of branches](#merging-of-branches)
5. [Tags and Commits](#tags-and-commits)
6. [Stash command and Hooks](#stash-command-and-hooks)
7. [Agiles Methodologies | Scrum](#agiles-methodologies-|-scrum)
8. [Bibliography](#bibliography)

<!--What is git?-->

## Git

<em> What is git? </em>

Git is a version control system. What is "version control"? It is a system that records changes made to a project over time.

Imagine you are writing an essay in a Word document and you want to have a record of all the changes you make. Every time you make a major modification to the essay, instead of saving the file under a different name, such as "essay_v1.doc", "essay_v2.doc", and so on, you use Git.

With Git, you create a repository for your test...but What is a repository? A repository is like a secure repository where all the versions and changes you've made to your files are stored. So every time you make changes, Git saves a "snapshot" of the current state of the test. Let's say you made changes and saved a snapshot called "Rehearsal_v1".

After that, you can continue editing the test and make more changes. When you are satisfied with the new changes, Git will save the differences between the current version and the previous snapshot. This way, you can keep track of the changes without duplicating the entire file.

If at some point you want to go back and see what your test looked like in version "Test_v1", Git allows you to do that easily. Also, if you are working with other people on the test, Git allows you to merge the changes that each person makes, avoiding conflicts whenever possible.

<!--Most common commands -->

## Basic commands

Some basic Git commands are:

```
git init
git status
git add
git commit
git push
git pull
git log
```
Use `git init` to create a new Git repository in a directory. It's like telling Git that you're starting to track changes in that directory and you want to make it a Git repository.

Use `git status` when you want to know what is going on in your Git repository. It's like asking Git: "What has changed since the last time I checked out?" With this command, you can get information about the current state of your repository.

Use `git add` to add files. By running `git add`, you tell Git that you want to add changes to specific files so that they are ready to be saved. It's like putting those files in a special box called a "staging area" before saving them permanently.

Use `git commit` when you want to save your changes to the Git repository permanently. It's like taking a "snapshot" of your modifications and with a descriptive message, you save that version in your project history.

Use `git push` to push your local changes to a remote repository. It is useful for sharing your changes with other collaborators, collaborating on a project or backing up your work to an external server.

Use `git pull` when you want to get the latest changes from a remote repository and merge them with your local version of the project. It's like synchronizing your work with updates made by other contributors.

Use `git log` to view the history of commits in a Git repository. It provides a detailed list of commits made, including information such as author, date, commit message and a unique identifier.

<!--Branches and Merging of branches-->

## Branches

<em> What are branches? </em>

Branches are independent lines of development that allow you to work on different features or solutions in parallel. Each branch represents a different version of the repository, and changes made in one branch do not directly affect the other branches.

To create a new branch, use the command `git branch <branch name>`. For example, if you want to create a branch named "develop", run the following command:

```
git branch develop
```

This will create the new branch, but will not change your current location. You will still be in the same branch you are currently in.

To start working on the new branch, you must switch to it. You can use the `git checkout <branch name>` command to do this. For example, if you want to switch to the "develop" branch, run:

```
git checkout develop
```

You will now be in the new branch and will be able to start making changes and commits specific to that branch.

**It is a good practice to keep the main branch stable and create separate branches to work on new features. This facilitates team collaboration and tracking of changes in the repository.**

## Merging of branches 

<em> What does branch merging mean? </em>

Branch merging is the process of combining changes made in one branch with another. Merging is useful when you want to incorporate changes from a secondary branch into the main branch of the project.

<em> How do I make a branch merger? </em>

1. Make sure you are on the target branch: Before merging a branch, switch to the branch where you want to incorporate the changes. For example, if you want to merge the "develop" branch into the "main" branch, make sure you are on the "main" branch.

```
git checkout main
```

2. Start the merge process: Use the command `git merge <merge branch name>` to start the merge. For example, to merge the branch "develop" into the current branch, run the following command:

```
git merge develop
```

**No further action is required after Git has completed the merge without conflicts but what do I do if a conflict happens?**

Then we can continue with these steps :

3.  If Git finds conflicts during the merge, it will notify you and show you the affected files. You will need to open those files and manually resolve the conflicts. The conflicts are indicated by special markers in the files, and you will have to choose which changes to keep or merge.

Once you have resolved the conflicts, you must mark them as resolved by running `git add <filename>` for each file with conflicts.

4. Once you have resolved all conflicts, you can complete the merge by running the `git commit` command. Git will automatically create a commit message for the merge.

After the merge is complete, the changes from the merged branch will be incorporated into the target branch and will be available there.

It is important to note that it is advisable to merge branches in a stable state, which means that there should be no pending changes or errors in the target branch. In addition, it is a good practice to perform extensive testing after the merge to make sure that everything works correctly.

<!--Etiquetas y confirmaciones-->

## Tags and Commits 

Both tags and commits are essential elements in Git for change tracking and version control in a repository.

Tags are static pointers used to mark specific points in the repository history.

There are two main types of tags in Git:

Annotated Tags: Annotated tags contain additional information, such as the author's name, creation date, and a descriptive message. They are created using the command `git tag -a <tag name> -m "<message>" <commit identifier>`.

Lightweight Tags: Lightweight tags are simply names for a specific commit, with no additional information. They are created using the command `git tag <tag name> <commit identifier>`.

Commits are snapshots of changes made to a repository. Each commit represents a point in the repository's history and contains information about changes made, such as file additions, modifications or deletions.

Use the command `git commit -m "<commit message>"`. Be sure to replace `<commit message>` with a clear and concise description of the changes made in this commit.

<!--Comando stash y ganchos-->

## Stash command and Hooks

The "stash" command in Git allows you to temporarily save changes that are not yet ready to be committed.

When you run `git stash`, Git saves your modified files and staged changes in a hidden area, allowing you to revert your working directory to a clean state. You can then switch branches or perform other operations. Later, you can reapply the saved changes using `git stash apply` or `git stash pop`. However, there is an important difference between them:

git stash apply: This command applies the changes from the most recent stash without removing it from the stash stack. The changes are applied in your working directory and are reflected in your changed files and in the staged changes you had before you stashed.

```
git stash apply
```

git stash pop: This command also applies the changes from the most recent stash, but unlike git stash apply, it removes that stash from the stack after applying it. When you run this command, the changes are applied to your working directory and are reflected in your modified files and staged changes. In addition, the corresponding stash is removed from the stash stack.

```
git stash pop
```

<!--Git branching strategies and flows.-->

## Git branching strategies and flows.

<!--Git rebase and squash | merge vs rebase.-->

## Git rebase and squash | merge vs rebase.

<!--Agiles Methodologies | Scrum-->

## Agiles Methodologies | Scrum

Agile methodologies are project management approaches that focus on flexibility, adaptability and collaboration. These methodologies are based on principles and values that value early and continuous delivery of functional software, effective communication, customer collaboration, and responsiveness to change.

Scrum is one of the most popular and widely used agile methodologies. It focuses on the management and organization of software development teams, especially in complex environments with changing requirements. It is designed to facilitate the rapid and regular delivery of software increments, and is based on an iterative and incremental approach.

+ Roles: Scrum defines three main roles: the Product Owner, the Scrum Master and the Development Team. The Product Owner represents the interests of the customer and manages the product backlog. The Scrum Master ensures that Scrum principles and practices are followed and helps the team to be efficient. The Development Team is responsible for delivering work in product increments.

+ Sprints: Sprints are fixed-time iterations in which product development takes place. Typically, a sprint lasts from 1 to 4 weeks. During each sprint, the team selects a set of items from the product backlog and commits to deliver them by the end of the sprint.

+ Product backlog: The product backlog is a prioritized list of all desired features, requirements and enhancements for the product. It is managed by the Product Owner and is refined and adjusted as more information is obtained.

+ Scrum Meetings: Scrum establishes different meetings to facilitate collaboration and communication. Some of these meetings include sprint planning, daily standup, sprint review and sprint retrospective.

Scrum encourages transparency, inspection and continuous adaptation. It focuses on delivering value to the customer quickly and consistently, and allows for the incorporation of changes and feedback throughout the development process.

<!--Bibliography-->

## Bibliography

* [Git Pages](https://git-scm.com/)
* [Get started with GitHub.](https://docs.github.com/en/get-started/quickstart/hello-world)
* [About Git](https://docs.github.com/en/get-started/using-git/about-git)
* [Scrum](https://www.atlassian.com/agile/scrum)