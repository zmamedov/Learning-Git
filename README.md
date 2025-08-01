# [Course Hexlet of studying Git basics](https://ru.hexlet.io/courses/intro_to_git)

<img src="icons/git.jpg">

----------
### Initial setup (git config)

1. ```git config --list --show-origin``` - to show all settings and where they are set.
2. ```git config --global user.name "John Doe"``` - set global user name (every commit has this information).
3. ```git config --global user.email "johndoe@example.com"``` - set global user email.
4. ```git config --local user.name "John Doe"``` - set local user name for certain project (initially need to go to this project).

----------

### Create Git repository

<img src="icons/git-init.jpeg" width="400" height="180">

1. ```git init``` - create new Git repository — directory `.git`, that contains all necessary Git-files.

> Command ```git init``` have to call in directory with a project.

2. ```git remote add origin <URL>``` - to link local repository and remote. "Origin" - short name of URL remote repository.

<img src="icons/git clone.png" width="400" height="180">

3. ```git clone <URL repository>``` - to clone remote repository.

> Instead `URL repository` may be used `SSH repository`.

----------

### Commit

<img src="icons/stage.webp" width="500" height="250">

1. ```git status``` - status of repository.
2. ```git add <filename>``` - to add the file to the index.
3. ```git add .``` - to add all files to the index.
4. ```git commit -m 'message'``` - to commit changes.
5. ```git commit --amend -m 'new message'``` - to rename last commit.
6. ```git push origin <branch name>``` - uploads all local branch commits to the corresponding remote branch.

> ```git push -u origin <branch name>``` - for first push. Git remembers that we work with repository "origin", branch "branch name". Now it can be used just ```git push```.

7. ```git pull``` - to fetch changes from remote repository and integrate them with a local branch. This command is the unions of 2: ```git fetch``` and ```git merge```.

----------

### Remove changes

<img src="icons/git restore.png" width="6000" height="250">

1. ```git clean -fd``` - to remove untracked files from the working tree.
2. ```git restore <filename>``` - to cancel changes in the modified file in the indesx (Changes not staged for commit).
3. ```git restore --staged <filename>``` - to cancel the index, don't modify file.(From "Changes to be committed" again to "not staged").
4. ```git rm --cached <filename>``` - to delete a file from  tracked (new status file - untracked).
5. ```git rm --cached .``` - all files.

----------

### History of commits

<img src="icons/git diff.jpg" width="400" height="180">

1. ```git diff``` - to show changes betwwen was and is.
2. ```git log``` - to enumerate commits (last commits a the top).
3. ```git log --oneline``` - to show commit in one line.
4. ```git show <hash commit>``` - to show all changes within the specified commit.
5. ```git blame <file>``` - to show last user that changed every line in the file.
6. ```git grep "line"``` - to search "line" in Git repository.

----------

### Revert commits

<img src="icons/git revert.png" width="400" height="180">

1. ```git revert <hash commit>``` - to create new commit that cancel specified commit.
2. ```git revert HEAD``` - to cancel last commit (quit from the editor - ":q!").
3. ```git revert HEAD --no-edit``` - to cancel last commit without editor vim.
4. ```git reset --hard HEAD~2``` - to cancel 2 last commits.

----------

### Branches

1. ```git checkout <branch>``` - to switch on branck "branch".
2. ```git checkout -b <branch>``` - to create branch "branch" and switch on it.
3. ```git branch <branch>``` - to create branch "branch".
4. ```git branch``` - to display list of branches.

----------

### Merging branches

<img src="icons/git merge.png" width="400" height="220">

1. ```git merge <branch>``` - to integrate changes from the branch "branch" into the current branch.
2. ```git rebase master``` - to integrate changes from a current branch onto "master" by moving a series of commits.

----------

### Stash

1. ```git stash``` - to hide all local changes and revert the working directory to the `HEAD` commit.
2. ```git stash pop``` - to return hidden changes.
