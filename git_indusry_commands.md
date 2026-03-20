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
git add -p
-p means patch mode
y → stage this part
n → skip it
s → split into smaller parts
q → quit
Why use it?
Make clean commits
Separate features and fixes
Avoid committing unwanted changes
git add -p lets you stage only selected parts of your changes
# git restore
git restore = Discard changes in your working directory
# syntax
git restore
Like “undo” button for your file changes
# git restore --staged
Used to remove files from the staging area (undo git add)
git restore --staged = Unstage the file (but keep changes in file)
Easy Analogy
Like taking an item out of your shopping cart
(you still have it, but not ready to buy)
# git rm
Used to delete a file from your project and Git tracking
git rm = Remove file from Git + delete it from folder
# syntax
git rm file.txt
# remove only from git
git rm --cached file.txt
# force remove
git rm -f file.txt
Removes even if there are changes
# git mv
Used to move or rename a file and track it in Git
# syntax
git mv oldname.txt newname.txt
File is moved + staged
git mv file.txt folder/file.txt-for file move
## commit commands
# git commit
--it is used to move the all files from the staging area to the local repo by using the commit 
# syntax
git commit-then it opens the text editor for the commit message
# git commit -m
it is same as git commit but the only chnage is -m means the message for the commit
# syntax
git commit -m "message"
# git commit --amend
Used to modify the last commit
git commit --amend = Edit your most recent commit
Important Note 
Only affects last commit
Avoid using after pushing
ex:git commit --amend -m "message"
# git commit --no-edit
Used to commit changes without changing the previous commit message
--no-edit = Keep the existing commit message
## Branch Management Commands
# git branch 
-it shows all local branches
# syntax
git branch
# git branch -a
-it shows all branches local and remote
# syntax
git branch -a
# git branch -d
-it delete the branch safely only if it is already merged
# syntax
git branch -d <branchname>
# git branch -D
-it deletes a branch even not merged
# syntax
git branch -D <branchname>
# git checkout
-it is used switch to the another branch
# syntax
git checkout <branchname>

# git checkout -b
-it is used to create a new branch and automatically switched to newly created branch
# syntax
git checkout -b <branchname>

# git switch
it is the modern switch command to switch the branch
# syntax
git switch <branchname>

# git switch -c
it is the modern cmd for the git checkout -b 
# syntax
git swicth -c <branchname>
 ## merge and Integration commands
 # git merge
 -Used to combine changes from one branch into another
 # syntax
 git merge <brachname>
 Step 1: You have two branches
main
feature
git switch main
git merge feature
# before
main:     A---B
feature:       C---D
# after 
main:     A---B---C---D
#  git merge --no-ff
Used to force Git to create a merge commit, even if fast-forward is possible
--no-ff = Always create a separate merge commit
# before
main:    A---B
feature:      C---D
# after
main:    A---B-------M
                 \   /
                  C---D
Why use it?
Keeps branch history clear
Shows that a feature branch was merged
Useful in team projects
git merge --no-ff forces a merge commit to preserve branch history
## remote repository  commands
# git remote
it shows repository name slike origin
# syntax
git remote
# git remote -v
it shows remote urls (fetch+push links)
# syntax
git remote add

# git remote add
Add new remote repo 
git remote add connects your local repo to a remote repository using a name
# syntax
git remote add <somename like origin> <github url>
# git remote remove
Used to delete a connection between your local repo and a remote repo
# syntax
git remote remove <somename like origin>

What happens?
Git forgets the GitHub repo link
Your local project remains 
When to use?
Wrong remote URL added 
Want to connect to a new repo 🔁
Cleaning up old remotes
easy analogy:
Like deleting a saved contact from your phone
# git fetch 
Downloads chnaes from remote to local repo and does not merge to the working directory
# syntax
git fetch
# git fetch --all
fetch from all remotes
git fetch --all downloads updates from all remotes without merging them
# syntax
git fetch --all
# git pull
it is fetch+merge
it dirctly download the changes from the remote repo to working directory
# syntax
git pull
# git pull --rebase
Fetch latest changes + reapply your commits on top (no merge commit)
git pull --rebase = Update your branch while keeping history clean
# before
Remote:   A --- B --- C
Local:    A --- B --- D --- E
# after with rebase
A --- B --- C --- D --- E
# after without rebase
A --- B --- C
         \     
          D --- E
               \
                M (merge commit)
Why use it?
Keeps history linear and clean
Avoids unnecessary merge commits
Easy Analogy
 Like inserting your work after the latest version instead of mixing it
 git pull --rebase updates your branch by placing your changes on top of the latest remote commits
 # git push
 -it is used to transfer the data from the local repo to remote repo
 # syntax
 git push
 # git push -u origin branch-name
 Upstream is the remote branch linked to your local branch for automatic push/pull
 -if you switch the branch and after that if you push with the upstream then after no need to mention specifically push or pull on this particular branch only
 # syntax
 git push -u origin branch_name
 # git push --force
 Used to forcefully update the remote repository by overwriting its history
 What it does
Overwrites remote history
Deletes commits on remote
Replaces with your local 
## stash commands
# git stash
Now suddenly:
Your manager asks you to fix a bug in production
But your work is incomplete — you don’t want to commit it yet.
Purpose:
Temporarily save your current changes and clean your working directory.
What happens:
Saves changes in a hidden stack
Reverts files back to last commit
# syntax
git stash
# git stash list
it shows the all saved stashes
# syntax
git stash list
# git stash apply
Apply a stash without removing it from stash list
You want to reuse the same stash again later
# syntax
git stash apply stash@{0}
# git stash pop
apply the stash and remove it from stash list
# syntax:
git stash pop
# difference
Command	Applies changes	Removes stash
apply	      ✅	            ❌
pop	           ✅	            ✅

# git stash drop
it is used to delete the specific stash from the stack
# syntax
git stash drop stash@{0}
You don’t need that saved work anymore
# git stash clear
delete all stashes
Warning: This is irreversible
# syntax
git stash clear
## reset and undo commands
# git reset
Move HEAD to a previous commit (undo commits)
if you do commit1 and then commit2 after that if you use the git reset command then it undo to the commit1
# syntax
git reset

# git reset --soft
it undo the commit but keep the chnages in staging area
# syntax
git reset --soft HEAD~1
 Result:
 Commit removed
 Changes still staged
 You can recommit easily
 # git reset --mixed
 Undo commit + unstage changes
 Result:
❌ Commit removed
❌ Not staged
✅ Changes still in working directory
# git reset --hard 
Completely remove commit AND changes
Result:
❌ Commit deleted
❌ Changes deleted
❌ Working directory cleaned
# syntax
git reset --hard HEAD~1

 git stash
• git stash list
• git stash pop
• git stash apply
• git stash drop
• git stash clear explain these with an example and what is the purpose of these things

Great question—git stash is very useful when you're working and suddenly need to switch context without committing unfinished code.

🔹 What is git stash (Purpose)
git stash temporarily saves your uncommitted changes (both staged + unstaged) and gives you a clean working directory.

👉 Think of it like:

“Pause my current work, keep it safe, and let me do something else.”

🧠 Real-Life Example Scenario
You are working on a feature:

git status
Output:

modified: app.js
modified: styles.css
Now suddenly:
👉 Your manager asks you to fix a bug in production

But your work is incomplete — you don’t want to commit it yet.

🔹 1. git stash
✅ Purpose:
Temporarily save your current changes and clean your working directory.

git stash
💡 What happens:
Saves changes in a hidden stack

Reverts files back to last commit

Now:

git status
Output:

nothing to commit, working tree clean
🔹 2. git stash list
✅ Purpose:
Shows all saved stashes

git stash list
Output:

stash@{0}: WIP on main: abc123 added login feature
stash@{1}: WIP on main: xyz456 updated UI
👉 Think of it like a stack (latest = top)

🔹 3. git stash apply
✅ Purpose:
Apply a stash without removing it from stash list

git stash apply stash@{0}
💡 Use case:
You want to reuse the same stash again later

🔹 4. git stash pop
✅ Purpose:
Apply the stash and remove it from stash list

git stash pop
💡 Difference from apply:
Command	Applies changes	Removes stash
apply	✅	❌
pop	✅	✅
🔹 5. git stash drop
✅ Purpose:
Delete a specific stash

git stash drop stash@{0}
💡 Use case:
You don’t need that saved work anymore

🔹 6. git stash clear
✅ Purpose:
Delete all stashes

git stash clear
⚠️ Warning: This is irreversible

🔥 Full Workflow Example
# Step 1: Work in progress
git status

# Step 2: Save work
git stash

# Step 3: Fix bug in another branch
git checkout bug-fix
# do work and commit

# Step 4: Come back
git checkout main

# Step 5: Restore work
git stash pop
🎯 Summary (Simple Way)
Command	Meaning
git stash	Save current work temporarily
git stash list	Show saved work
git stash apply	Apply stash (keep it saved)
git stash pop	Apply + remove stash
git stash drop	Delete one stash
git stash clear	Delete all stashes
💡 Easy Analogy
Think of git stash like:

📦 Packing your work in a box

🧹 Clean your room (working directory)

📤 Take it back when needed

If you want, I can also show:
✅ git stash with message
✅ git stash for specific files
✅ Common mistakes students make with stash

Just tell me 👍


 git reset
• git reset --soft
• git reset --mixed
• git reset --hard
• git revert
• git clean -f
• git clean -fd    explain the purpose with an examples

These are very important Git commands—they control how you undo changes. I’ll explain each one clearly with a simple example + purpose + effect.

🧠 First Understand 3 Areas in Git
Before learning reset, you must know:

Working Directory → your files (what you edit)

Staging Area (Index) → what you added using git add

Repository (Commit history) → saved commits

🔥 Example Setup
Let’s say you did:

echo "v1" > file.txt
git add file.txt
git commit -m "First commit"

echo "v2" >> file.txt
git add file.txt
git commit -m "Second commit"
👉 Now history:

Commit A → Commit B (HEAD)
🔹 1. git reset
✅ Purpose:
Move HEAD to a previous commit (undo commits)

git reset HEAD~1
👉 Equivalent to --mixed by default

🔹 2. git reset --soft
✅ Purpose:
Undo commit BUT keep changes in staging area

git reset --soft HEAD~1
💡 Result:
❌ Commit removed

✅ Changes still staged

👉 You can recommit easily

🧠 Example:
Before:

Commit A → Commit B
After:

Commit A
(staged changes from B are still there)
🔹 3. git reset --mixed (default)
✅ Purpose:
Undo commit + unstage changes

git reset --mixed HEAD~1
💡 Result:
❌ Commit removed

❌ Not staged

✅ Changes still in working directory

🧠 Example:
Changes are now like you just edited the file
🔹 4. git reset --hard
✅ Purpose:
Completely remove commit AND changes

git reset --hard HEAD~1
💡 Result:
❌ Commit deleted

❌ Changes deleted

❌ Working directory cleaned

⚠️ Dangerous (data loss)

🧠 Example:
Commit A → Commit B
After:

Commit A only (B gone forever)
🎯 Reset Summary
Command	Commit	Staging	Working Dir
soft	❌removed	✅ kept	✅ kept
mixed	❌ removed	❌ removed	✅ kept
hard	❌ removed	❌ removed	❌ removed
# git revert 
Undo a commit safely safely by creating a new commit
result:
keeps the history safe 
adds a new commit that reverses chnages
# before
A → B → C
# after
A → B → C → D (revert of C)
# syntax
git revert
# git clean -f
it removes the untracked files
# before
tracked: file.txt
untracked: temp.txt
# after
temp.txt deleted
# syntax:
git clean -f

# git clean -fd
Remove:
untracked files
untracked directories
# before
temp.txt
build/
# after
Both deleted

## Rebasing commands
# what is git rebase?
Move or reapply your commits on top of another branch
# simple example
# before
A → B → C   (main)
     \
      D → E (feature)
# rebase
A → B → C → D → E
# git rebase 
Reapply commits on top of another base
# syntax
git rebase <branchname>
# git rebase -i
Edit commit history (very powerful)
# syntax
git rebase -i HEAD~3
# git rebase --continue
Continue rebase after resolving conflicts
# syntax
git rebase --continue

# git rebase --abort
cancel the rebase and go back t original state
# syntax
git rebase --abort
Use case:
Too many conflicts
Something went wrong
# important rule
 NEVER use rebase on already pushed commits (shared branch)
 # summary
 Command	Purpose
git rebase	Move commits to new base
git rebase -i	Edit commit history
git rebase --continue	Continue after fixing conflict
git rebase --abort	Cancel rebase
## cherrypick and patch cmd
# git cherry-pick
Copy a specific commit from one branch and apply it to another branch
# example
main:     A → B → C
feature:        D → E
You only want commit D in main
# after
git checkout main
git cherry-pick <commit-hash-of-D>
# result
main: A → B → C → D
Real use case:
Fix applied in one branch → need same fix in another branch

# git format-patch
convert the commits into patch files(.patch)
Used for sharing changes via files (email, offline, etc.)
# example
git format-patch -1 HEAD
0001-Added-login-feature.patch-creats file like
# syntax:
git format-patch -1 HEAD

# git apply
Apply a patch file without creating a commit
# example
git apply 0001-Added-login-feature.patch
Result:
Changes are added to working directory
❌ No commit created

# git am
Apply patch AND automatically create commit
Used with patches created by git format-patch
Result:
Changes applied
 Commit created with original message & author
 Difference: apply vs am
Feature	git apply	git am
Applies patch	✅	✅
Creates commit	❌	✅
Keeps author info	❌	✅
