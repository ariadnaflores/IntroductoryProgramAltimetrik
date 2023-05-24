# IntroductoryProgramAltimetrik

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


## Merging of branches 


<!--Etiquetas y confirmaciones-->
<!--Comando stash y ganchos-->


