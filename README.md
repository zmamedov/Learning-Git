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
5. ```git push origin <branch name>``` - uploads all local branch commits to the corresponding remote branch.

> ```git push -u origin <branch name>``` - for first push. Git remembers that we work with repository "origin", branch "branch name". Now it can be used just ```git push```.

6. ```git pull``` - to fetch changes from remote repository and integrate them with a local branch. This command is the unions of 2: ```git fetch``` and ```git merge```.

----------

### Remove changes

<img src="icons/git restore.png" width="6000" height="250">

1. ```git clean -fd``` - to remove untracked files from the working tree.
2. ```git restore <filename>``` - to cancel changes in the modified file in the indesx (Changes not staged for commit).
3. ```git restore --staged <filename>``` - to cancel the index, don't modify file.(From "Changes to be committed" again to "not staged").
4. ```git rm --cached <filename>``` - to delete a file from  tracked (new status file - untracked).
5. ```git rm --cached .``` - all files.

----------

### Анализ истории изменений

1. ```git diff``` - показывает разницу между тем, что было и что стало.
2. ```git log``` - список всех выполненных коммитов по дате добавления.
3. ```git log --oneline``` - сокращенный вывод.
4. ```git show <хеш коммита>``` - все изменения, сделанные в рамках одного коммита.
5. ```git blame <file>``` - кто последним менял конкретную строчку в файле.
6. ```git grep line``` - в каком файле есть данная строка <line>.

----------

### Отмена изменений

1. ```git revert <хеш коммита>``` - создание еще одного коммита, который выполняет изменения, противоположные тому коммиту, который отменяется.
2. ```git revert HEAD``` - откатывает последний коммит (HEAD - текущее состояние). Выйти из редактора - ":q!".
3. ```git revert HEAD --no-edit``` - откатывает последний коммит без открытия реадктора vim.
4. ```git reset --hard HEAD~2``` - <u>удалить</u> 2 последних коммита.

----------

### Ветки

1. ```git checkout <branch>``` - переключиться на ветку branch.
2. ```git checkout -b <branch>``` - создать ветку branch и переключиться на неё.
3. ```git branch <branch>``` - создать ветку branch.
4. ```git branch``` - посмотреть список веток.

----------

### Слияние веток

1. ```git merge <branch>``` - перенести все изменения из ветки <branch> в ту ветку, где <u>**сейчас находимся**</u>.

----------

### Stash

1. ```git stash``` - прячет все изменения независимо от того, добавлены ли файлы в индекс или нет (кроме Untracked файлов).
2. ```git stash pop``` - вернуть спрятанные изменения.
> Stash в Git работает по принципу стека. Он позволяет сохранить внутрь любое количество изменений и восстановить их в обратном порядке.