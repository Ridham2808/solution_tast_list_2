### **Part 1: Git Basics**

#### **Task 1: Install and Configure Git**
1. Install Git from [git-scm.com](https://git-scm.com/).  

2. Configure your global Git settings:  
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "your-email@example.com"
   ```
* Answer :- git config --global command is use for set and manage configuration settings, like user name, email.

3. Verify the configuration:  
   ```bash
   git config --list
   ```
* Answer:- --list command is use for get detais of configuration settings which are active.

#### **Task 2: Initialize a Repository**
1. Create a directory and initialize it as a Git repository:  
   ```bash
   mkdir MyProject
   cd MyProject
   git init
   ```
   - **Purpose**: Initializes a `.git` folder to track changes.
* Answer:- Make new folder name MyProject and go to the folder and initialize it repo.
---

### **Part 2: Basic Workflow**

#### **Task 3: Creating and Committing Files**
1. Create a file:  
   ```bash
   echo "Hello Git" > file1.txt
   ```
* Answer:- Createting a new file named File1.txt

2. Stage and commit the file:  
   ```bash
   git add file1.txt
   git commit -m "Initial commit: Added file1.txt"
   ```
* Answer:- Add new to staging area and commit it.

#### **Task 4: Viewing Changes**
1. Modify the file:  
   ```bash
   echo "Git is awesome!" >> file1.txt
   ```
* Answer:- Make Changes in file.
2. Check file status and differences:  
   ```bash
   git status
   git diff
   ```
* Answer:- git status = this command shows the current state of the working directory and staging area. also tells that which files are modifieded,untracked,stage for commit.
* Answer:- git diff = show changes of file.

#### **Task 5: Undoing Changes**
1. Unstage a staged file:  
   ```bash
   git reset file1.txt
   ```
* Answer:- git reset command removes file from staging area,basically its use when we staged the file accidently and want to unstaged it without losing edits of file.

2. Discard uncommitted changes:  
   ```bash
   git checkout -- file1.txt
   ```
* Answer:- git checkout -- {file name} command discard uncommitted changes means its delete latest changes and go back to last commited message.
---

### **Part 3: Branching and Merging**

#### **Task 6: Branch Management**
1. Create a branch and switch to it:  
   ```bash
   git checkout -b feature-branch
   ```
* Answer:- create a new branch and directly stitch in it.

2. List branches:  
   ```bash
   git branch
   ```
* Answer:- For get all branches list.

3. Rename a branch:  
   ```bash
   git branch -m feature-branch feature-enhanced
   ```
* Answer:- reaname a branch . fearure-branch name changes to feature-enhanced.

#### **Task 7: Merging Branches**
1. Merge `feature-enhanced` into `main`:  
   ```bash
   git checkout main
   git merge feature-enhanced
   ```
* Answer:- go to main branch and merg it with feature-enhanced branch.  

#### **Task 8: Handling Merge Conflicts**
1. Create two conflicting branches and resolve a conflict manually:  
   ```bash
   git merge <branch-name>
   ```
2. Use:  
   ```bash
   git add <resolved-file>
   git commit
   ```
* Answer:-

  * Create conflicting branches named branch1 and branch2.

  * Merge and manually edit the file to resolve conflicts.

  * Uses git add <resolved-file> to stage the resolved file.

  * Commit the resolved merge with git commit.

---

### **Part 4: Remote Repositories**

#### **Task 9: Remote Setup**
1. Add a remote repository:  
   ```bash
   git remote add origin https://github.com/your-username/repo.git
   ```
* Answer:- add remote repo.

2. Verify the remote:  
   ```bash
   git remote -v
   ```
* Answer:- git remote -v command used for get the list of all the remote repositories which are connected to the local Git repository,with their URLs. The -v flag shows both fetch and push URLs for each remote.

#### **Task 10: Push and Pull**
1. Push changes to the remote repository:  
   ```bash
   git push -u origin main
   ```
* Answer:- push file from local to globle.

2. Pull changes from the remote:  
   ```bash
   git pull origin main
   ```
* Answer:- pull file from globle to local.

#### **Task 11: Cloning a Repository**
1. Clone a remote repository:  
   ```bash
   git clone https://github.com/your-username/repo.git
   ```
* Answer:- copy the repo from globle to local.

---

### **Part 5: Advanced Git**

#### **Task 12: Stashing Changes**
1. Save uncommitted changes:  
   ```bash
   git stash
   ```
* Answer:- This command is use for save temporarily uncommitted changes. which means it's leaves working directory clean that allowing to switch branches or work on something else.

2. Apply stashed changes:  
   ```bash
   git stash apply
   ```
* Answer:- This command restores latest stashed changes back to working directory but keeps the stash saved for future use.

3. Drop the stash:  
   ```bash
   git stash drop
   ```
* Answer:- This command deletes the latest stash from the stash list.which means that we have to use this after make a change and don't want it again.

#### **Task 13: Tagging Commits**
1. Create and annotate a tag:  
   ```bash
   git tag -a v1.0 -m "Version 1.0 release"
   ```
* Answer:- creates an annotated tag named v1.0 with a message "Version 1.0 release.

2. Push the tag to the remote:  
   ```bash
   git push origin v1.0
   ```
* Answer:- push the tag v1.0.

#### **Task 14: Rewriting Commit History**
1. Use interactive rebase to modify commit messages:  
   ```bash
   git rebase -i HEAD~3
   ```
   - Replace `pick` with `edit` or `squash` as needed.
* Answer:- 

   -i :- it means that it allows you to modify,reorder ,give full control over how the commit history looks.

   HEAD~3 :-This specifies The interactive rebase will only apply to last 3 commits.

#### **Task 15: Cherry-Picking Commits**
1. Apply a specific commit to another branch:  
   ```bash
   git cherry-pick <commit-hash>
   ```
* Answer:- This command takes a specific commit from another branch and applies it to current branch.in short it means that its copy text from another branch without merging it.   

---

### **Part 6: Collaboration**

#### **Task 16: Forking and Pull Requests**
1. Fork a repository and clone it locally:  
   ```bash
   git clone https://github.com/your-username/forked-repo.git
   ```
2. Make changes and push them:  
   ```bash
   git checkout -b fix-typo
   echo "Typo fixed" >> README.md
   git commit -m "Fixed a typo"
   git push origin fix-typo
   ```
3. Open a pull request on GitHub.
* Answer:- 

  * Fork: Forking a repository on GitHub creates a copy of someone else's repository under your own GitHub account.
  * git clone : This command clones your forked repository from GitHub to your local machine.

  * git checkout -b : This command creates a new branch and switches to it.

  * echo "Typo Fixed" >> README.md: This command adds the text "Typo fixed" to the end of the README.md file.

  * git add README.md: Stages the README.md file for committ.

  * git commit -m "Fixed a typo": Commits the staged changes, with a message.

  * git push origin fix-typo: This command pushes fix-typo branch and its changes the fork on GitHub.

#### **Task 17: Simulating Team Collaboration**
1. Simulate a conflict by having two users modify the same file.  
2. Practice resolving the conflict as a team.

---

### **Part 7: Ignoring Files**

#### **Task 18: Using .gitignore**
1. Create a `.gitignore` file:  
   ```bash
   echo "node_modules/" > .gitignore
   git add .gitignore
   git commit -m "Added .gitignore"
   ```
* Answer:- create .gitignore file that tells Git to ignore the node_modules/ directory, so it won’t track or include it in commits. Then staged the file for commit. and commit file.

2. Verify that ignored files are not staged:  
   ```bash
   git status
   ```
* Answer:- this command shows the current state of the working directory and staging area. also tells that which files are modifieded,untracked,stage for commit.

---

### **Part 8: Automation and Cleanup**

#### **Task 19: Cleaning the Repository**
1. Remove untracked files:  
   ```bash
   git clean -f
   ```
* Answer:- This command delete untracked files from working directory.delete all files which are not added to git.

#### **Task 20: Aliases and Shortcuts**
1. Create an alias for frequently used commands:  
   ```bash
   git config --global alias.st status
   git config --global alias.cm commit
   ```
* Answer:- alias command is used for make shortcut.

   * above example shows it. which means, instead of typing git status,just type git st to check the status. and instead of typing git commit,just type git cm to commit changes.


2. Use the alias:  
   ```bash
   git st
   git cm -m "Message"
   ```
* Answer:- used the alias command.
   
  * git st means git status.
  * git cm -m "Message" means its commit changes with message.
---