# Git Configuration Commands

## Git Config User Name Command

### Syntax

git config --global user.name "Your Name"


### Purpose
Sets the username globally for Git. This name will appear as the author name in all commits.

### Example

git config --global user.name "Potnuru Jamuna"


---

## Git Config User Email Command

### Syntax

git config --global user.email "your-email@example.com"


### Purpose
Sets the email address globally for Git. Git uses this email to identify the author of commits.

### Example

git config --global user.email "durgayanamala638@gmail.com"


---

## Git Config List Command

### Syntax

git config --list


### Purpose
Displays all Git configuration settings currently set on the system.

### Example

git config --list


---

# 2. Repository Setup Commands

## Git Init Command

### Syntax

git init


### Purpose
Creates a new Git repository in the current directory.

### Example

git init


---

## Git Clone Command

### Syntax

git clone <repository-url>


### Purpose
Creates a copy of an existing remote repository on your local machine.

### Example

git clone https://github.com/user/project.git


---

## Git Clone Branch Command

### Syntax

git clone --branch <branch-name> <repository-url>


### Purpose
Clones a repository and checks out a specific branch.

### Example

git clone --branch main https://github.com/user/project.git


---

## Git Clone Depth Command

### Syntax

git clone --depth <number> <repository-url>


### Purpose
Clones a repository with limited commit hist…
## REpository Status and Inspection 
# 1.git status
## syntax
git status
-used to check the status of the repos
ex:git status
# 2.git log
## syntax 
git log
-used to give the recent commits
ex:git log
# 3.git log --oneline
## syntax
git log --oneline
-used to show the commit history in a short and simple format.
ex:git log --oneline
# 4. git log --graph
# syntax
git log --graph
-used to show the commits on a structured manner 
ex:git log --graph
# git show
# syntax
git show <specified commit name>
-used to get the details about the specified commit,if nothing is specified there then it is going to take the recent commited one
ex:git show "recent commit"
# git diff 
# syntax
git diff
-shows changes not yet staged
-there is different ways to use the diff here
1)git --staged-used to compare the staged changes
2)git --cached-shows changes that are added using git add but not commited,and it is also shows the difference between branches
git diff = before saving (preview changes)
git show = after saving (see committed changes)
git diff --name-only=>shows only file names changed
Key Role of git diff
👉 It helps you:
Review changes before committing
Debug mistakes
Understand modifications clearly
Avoid committing unwanted code
# git diff --staged:
 # syntax
git diff --staged
-see what changes are ready to be committed
--shows the chnags already staged fro commit
ex:git diff --staged

# git blame
# syntax
git blame <file_name>
-git blame is a command used to see who chnaged each line in a file and when,it helps you to track the history of every line of code
-it is used to find the who introduced a bug ,Understand who to ask about a piece of code,see when a line was changed,track history of specific lines
-git blame -n file.txt=>shows the line numbers
It shows the last person who modified the line, not the original creator.
If someone edits a line later, blame will show the latest editor.
# git reflog
git reflog = History of your actions in Git (like commits, resets, checkouts, etc.)
Why is it useful?
Sometimes you:
accidentally delete commits 
do a git reset --hard
switch branches and lose track
 git reflog helps you recover lost commits
# syntax
git reflog
# git shortlog
git shortlog is used to summarize commit history grouped by author.
It tells you:
Who contributed
How many commits each person made
# syntax
git shortlog
-git shortlog -s -n =>show only number of commits
ex:git shortlog
## File Tracking Commands
# git add
# syntax
 git add <filename>
-it is used to add the specific or all files to the staging area
ex:git add file.txt
# git add .
# syntax
git add .
-it is used to add all the files present in  the working directory to the staging area
ex:git add .
# git add -p
# syntax  

