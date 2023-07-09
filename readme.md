# Revisiting My Git Knowledge: Basics Of Git

## What is Git?

Git is indeed a widely used version control system that is popular among developers worldwide. It provides a robust and efficient way to manage code and collaborate with other programmers.

With Git, developers can track changes made to their code over time, create different branches to work on different features or bug fixes simultaneously, and merge those changes seamlessly. It offers a distributed architecture, allowing multiple developers to work on a project independently and then merge their changes together.

Overall, Git's popularity stems from its flexibility, speed, and powerful collaboration features. It has become the go-to version control system for many developers, enabling efficient code management and facilitating global collaboration in software development projects.

## Installing Git

Visit [Git SCM offical website](https://git-scm.com/download) to find out how to install Git on your OS (Operating System).

## Setting up Git

You can set up Git by using the following commands:

* `git config --global user.name "Full Name"`
* `git config --global user.email "youremail@emailprovider.com"`
* `git config --global user.username "your_github_username"`
* To enable helpful colorization of command line output use `git config --global color.ui auto` command.

You can use  `git config --global --list` command to find out you current global configurations.

> **Note:** Alternatively you can use `--local` parameter instead of `--global` to set these user details for the current repo directory you're in, instead for all repos in your pc.

## Using Git
>
> **Local:** Using Git locally on your pc.

1. Create a folder for your project, and create a Github repository for the project.

     > Note: The folder name can be different from the GitHub repository.

2. Open the terminal in your project folder and type `git init` to initialize a git repository.
3. Make the changes in the project folder, i.e. create, edit, delete files.
4. Use `git status` command to check the status of a repository (a.k.a repo).
5. Add changes to the Staging area with `git add "file name"` or add all changes to the Staging area by `git add .` command.
6. Commit the Staged changes by `git commit -m "Message for commit"`.

    **For example** `git commit -m "Created test.txt file"`

7. Remove files from the Staging area by `git restore --staged "file name"` or remove all changes from the Staging area by `git restore --staged .` command.
8. You can use the `git diff` command to show changes between commits, commit and working trees, etc.
9. Use `git diff first_branch second_branch` to find the difference between the two branches.

> **Branches:** Git repositories use branches to isolate work when needed. It's common practice when working on a project or with others on a project to create a branch to keep your working changes in. This way you can do your work while the main, commonly named `master`, branch stays stable. When the work on your branch is finished you merge it back into the `master` master branch.

> When you create a branch, Git copies everything from the current branch you're on and places it in the branch you've requested be made.

10. You can use `git branch` command to see all branches of the current repo.
11. You can create a new branch by using `git branch branch_name`.
12. You can switch to other branches by `git switch branch_name`.
13. You can create and switch to a branch with a single command as well `git switch -c branch_name` this will create and switch to `branch_name`.
14. You can rename the current branch by using `git branch -m new_name` or rename other than the current branch by `git branch -m old_branch_name new_branch_name`.

    **For example** `git branch -m master main` will rename the `master` branch to `main`.

> **Remote:** Using Git to work on remote projects.

15. You can have multiple remotes (i.e. Github repositories) so each requires a name. The primary remote is typically named `origin`.
    You can connect your repository to your remote repo i.e. Github Repository by using the following commands: `git remote add remote_name github_url`.

    **For example** `git remote add origin https://github.com/mumer012001/hello-world.git`
    **OR** If the remote named `origin` is already created then set the remote URL by using command:'git remote set-url origin github_url`.

16.  Use `git remote -v` command to see the connected remotes for the local repo.
17. You can pull the changes from the remote to the local repo by using `git pull remotename branchname`.

    **For example** `git pull upstream master` and you can also run `git fetch --dry-run` to see changes to the remote before you pull in.

18. You can push the changes from local to remote repo by using `git push remotename branchname`.

    **For example** `git push origin feature`.

19. You can Fork a project in Github by clicking on the Fork button which is the second button beside the Star button below the header on the top right side of the repo page.
20. You can clone any project by using the `git clone github_url` command.
21. If you clone a forked project, first check the remotes of the repo by using the `git remote -v` command.
    If there are 2 remotes `origin` and `upstream` then great. If otherwise, you need to add the `upstream` remote as well.
    > `upstream` remote is the original repo from which the cloned project is forked

22. You can add the upstream remote in the same way as you add the origin remote. 

    **For example** you need to run the following command:
    `git remote add upstream https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git`
    **instead of:**
    `git remote add origin https://github.com/YOUR_USERNAME/FORKED_REPOSITORY.git`
    > You can always verify that intended remotes are added by using the `git remote -v` command.

23. To add collaborators to one of your projects, visit the repository's page on your GitHub account and click the `Settings` tab in the menu in the upper part of the page. Then select the `Collaborators` option. Type the username into the text box add and click on the `Add` button.
24.  If you're working on something with someone else, then you need to stay up to date with the latest changes. So you'll want to pull in any changes that may have been pushed to the central GitHub repository by the `git pull remotename branchname` command.

> **Pull Requests:** Often when you make changes and improvements to a project you've forked, you'll want to send those changes to the maintainer of the original and request that they pull those changes into the original so that everyone can benefit from the updates—that's a pull request.

25. After your pull request is merged into the original repo on GitHub. You can merge your branch locally, too.

    For this, first move into the branch you want to merge into, **For example** `master` or `main` by using the `git switch main` command.

26. Now tell Git what branch you want to merge in, i.e. your feature branch. Use the `git merge feature_branch_name` command to merge the feature branch.
27. Now that the feature branch is merged, you might not need the feature branch anymore. You can delete the feature branch or any branch for that matter by using `git branch -d branch_name`.
28. You can also delete the branch from your remote on GitHub by using `git push remote_name --delete branch_name`.

    **For example** `git push origin --delete branch_name`.

29. The original has changed since your pull request was merged. If you pull in these changes from upstream you'll be up to date and have that version too.
30. Sometimes it may be a good idea to exclude files from being tracked with Git. This is typically done in a special file named `.gitignore`. You can add files and directories to be ignored in the `.gitignore` file.

> __*That's it for now, I'll update this repo when I remember something else to add.*__
