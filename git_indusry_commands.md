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

