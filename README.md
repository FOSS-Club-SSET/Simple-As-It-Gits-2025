# Simple As It Gits 2025 Curriculum

*"Simple as it Gits"* is a full-day, hands-on workshop on Git and GitHub, conducted by FOSS Club SSET.

## Table of Content

- [Module 1: Git Fundamentals & Local Workflow](#module-1-git-fundamentals--local-workflow)
- [Module 2: Branching & Merging](#module-2-branching--merging)
- [Module 3: GitHub Integration](#module-3-github-integration)
- [Module 4: Collaboration Workflow](#module-4-collaboration-workflow)
- [Module 5: Undoing Changes](#module-5-undoing-changes)
- [Module 6: Advanced Practices](#module-6-advanced-practices)


## Module 1: Git Fundamentals & Local Workflow
### Concepts Covered:

- Version control basics

- Repository initialization

- Staging/Committing

- Change tracking

```bash
```bash
```bash
git init # Start a repo
git status # Check file states
git add <file> # Stage a file
git add . # Stage all files
git commit -m "Message" # Save changes
git log # View history
git diff # Compare changes
```

### Installation & Initial Configuration

> [Use the official website](https://git-scm.com/) to download git

Setting up the global identity

```bash
# Configure author name
git config --global user.name "Alex Johnson"

# Configure author email
git config --global user.email "alex@example.com"
```

### Exercise:

1. Create a project folder with mkdir

```bash
mkdir my-first-git-repo # Create a new directory
cd my-first-git-repo # Navigate into the directory
```

2. Initialize Git repo

```bash
git init
```

3. Create README.md and write something

```bash
code .
```

4. Stage & commit
```bash
git add README.md # Stage README.md
git commit -m "My first commit" # Commit with a message
```

5. Check Log

```bash
git log # View commit history
```

6. Modify README.md then check status & diff

```bash
git status # Check file states
git diff # Compare changes
```

7. Stage, commit all changes and check log

```bash
git add . # Stage all changes
git commit -m "<message>" # Commit with a message
git log # View commit history
```

## Module 2: Branching & Merging

### Concepts Covered:

- Working with isolated branches

- Merging changes back to main

- Fast-forward vs. 3-way merges

- Resolving merge conflicts

```bash

CLI Commands:
git branch                     # List all branches
git branch <name>             # Create a new branch
git switch <branch>           # Switch to an existing branch
git switch -c <new-branch>    # Create and switch to a new branch
git merge <branch>            # Merge given branch into current branch
```

Exercise:
1. Create a new branch and switch to it
```bash
git switch -c feature-1       # '-c' creates the new branch and 'switch' command switches to it.
```
> You're now working on a new isolated branch named feature-1.

2. Make some change in the file and commit
```bash
git add feature.txt           # stages the file
git commit -m "Add feature 1" # commits the change
```

3. Switch back to the main branch
```bash
git switch main               # switches command switches it to main branch
```

4. Make some other conflicting change in the same file
```bash
git add feature.txt
git commit -m "Main branch change"
```

5. Try to merge feature-1 into main
```bash
git merge feature-1           # merges the 2 branches
```
> Since both branches changed the same file, Git will report a merge conflict.

6. Resolve the conflict manually
Open the conflicted file (e.g, feature.txt). It will look like this:

```txt
This is main branch change
This is feature 1
```
Edit the file to resolve the conflict:

```txt
This is main branch change
This is feature 1
```

7. Stage the resolved file and commit
```bash
```bash
git add feature.txt # Stage the resolved file
git commit -m "Resolve merge conflict between main and feature-1" # Commit the resolution
```

Bonus Tip: Delete a branch (after merging)
Once you've successfully merged a feature branch, you can delete it to keep your repo clean:

```bash
# Delete the feature-1 branch after merging
git branch -d feature-1 # Safely delete the branch if merged
```
> Use `-D` instead of `-d` to force delete if the branch hasn't been merged yet.
```
> Use -D instead of -d to force delete if it's not merged yet. ^_~
## Module 3: GitHub Integration
### Concepts Covered:

- Remote repositories

- Push/Pull workflow

- Clone vs. Fork
```bash
CLI Commands:

bash
git remote add origin <URL>     # Link local ↔ remote
git push -u origin main         # First push (set upstream)
git push                        # Subsequent pushes
git pull                        # Fetch + merge
git clone <URL>
```
### Exercise:

1. Create an account on [GitHub](https://github.com) and Create a GitHub repo  (no README/license)

Initialize a repository 
    
2. Connect local repo to GitHub
reference: https://docs.github.com/en/authentication/connecting-to-github-with-ssh
```bash
```bash
ssh-keygen -t ed25519 -C "your_email@example.com" # Generate a new SSH key
```
```bash
Enter file in which to save the key (/c/Users/YOU/.ssh/id_ALGORITHM):[Press enter] # Save the key in the default location
```
```bash
clip < ~/.ssh/id_ed25519.pub # Copy the public key to clipboard
```
In the upper-right corner of any page on GitHub, click your profile picture, then click Settings. # Navigate to GitHub settings

In the left sidebar: Access > SSH and GPG keys # Locate SSH and GPG keys section

Click New SSH key or Add SSH key. # Add a new SSH key

In the "Title" field, add a descriptive label for the new key. # Provide a label for the key

In the "Key" field, paste what was copied from the clip command. # Paste the copied public key

Click Add SSH key. # Save the new SSH key

```bash
git remote add origin git@github.com:YourUsername/YourRepository.git # Link local repository to GitHub
```
```bash
git push -u origin main # Push the main branch to GitHub and set upstream
```
If your local branch is named master, use:
```bash
git push -u origin master # Push the master branch to GitHub and set upstream
```

NOTE:
```git push``` uploads your commits to the remote repository for the branch you’re currently working in. # Push changes to remote repository

5. Clone a partner's repo
```bash
git clone git@github.com:partnerusername/their-repo-name.git # Clone a repository from a partner
```
```   

## Module 4: Collaboration Workflow

### Concepts Covered:

- Forking a repository on GitHub
- Cloning the forked repository
- Creating a new branch for changes
- Making and committing changes in the cloned repo
- Pushing changes to the forked GitHub repo
- Opening a Pull Request (PR)


Task:
Fork the [Simple As It Gits](https://github.com/FOSS-Club-SSET/Simple-As-It-Gits-2025) repo, clone it to your local machine, and add a `<your_name_scsnumber>.md` file in the participants folder.

### CLI Commands:

```bash
git clone    # Clone a repository to your local machine
git switch   # Switch branches or create a new branch
git add      # Stage changes for the next commit
git commit   # Save changes to the repository
git push     # Upload commits to a remote repository
```
```

---

### Exercise:

#### 1. Fork the Original Repository

- Go to the GitHub page of the [Simple As It Gits](https://github.com/FOSS-Club-SSET/Simple-As-It-Gits-2025) repository.
- Click on the *Fork* button in the upper-right corner.
- This will create a copy of the repository under your GitHub account.


#### 2. Clone the Forked Repository

```bash
git clone git@github.com:your-username/Simple-As-It-Gits-2025.git
cd Simple-As-It-Gits-2025/
```

#### 3. Create and Switch to a New Branch

```bash
git switch -c my-feature-branch # Create and switch to a new branch named 'my-feature-branch'
```

> This keeps your changes isolated from the main code.


#### 4. Navigate to participants folder

```bash
cd Participants
```

> This will navigate to folder Participants, residing inside the Simple-As-It-Gits-2025 repository.

#### 5. Create a new file and Make Changes

- Create a new file `<yourname_admission_number>.md` 
- Enter your name and a short sentence about yourself.
- Save your work.


#### 6. Stage and Commit Changes
```bash
git add . # Stage all changes
git commit -m "Add a meaningful commit message describing your change" # Commit with a descriptive message
```
```

#### 7. Push Your Branch to Your Fork

```bash
git push origin my-feature-branch
```

#### 8. Open a Pull Request (PR)

- Go to your forked repository on GitHub.
- You'll see a prompt to open a pull request for the pushed branch.
- Click *"Compare & pull request"*.
- Add a title and description for your changes.
- Click *"Create pull request"*.

> Now the project maintainers can review and merge your contributions!

---

## Module 5: Undoing Changes
### Concepts Covered:

- Commit history rewriting

- Stashing temporary work

```bash
CLI Commands:

bash
git restore <file>              # Discard uncommitted changes
git reset --soft HEAD~1         # Undo commit (keep changes)
git reset --hard HEAD~1         # Destroy last commit
git revert <commit-hash>        # Safe undo for shared history
git stash                       # Temporary shelf
```

### Exercise:

### Undo and recommit
- Make a change and commit it  
```bash
git reset --soft HEAD~1 # Undo the last commit but keep changes staged
```
- Modify the file and recommit the updated change  
```bash
git commit -m "Updated commit message" # Recommit the updated changes
```

### Discard Broken Code
- Intentionally break a file  
- Discard changes with:  
```bash
git restore <file> # Discard uncommitted changes in the specified file
```

### Revert a pushed commit
- Identify the hash of a commit already pushed  
```bash
git revert <commit-hash> # Create a new commit that undoes the changes from the specified commit
```
- Push the reverted commit to remote  
```bash
git push # Push the new revert commit to the remote repository
```

### Use git stash
- Make uncommitted changes  
```bash
git stash # Temporarily save uncommitted changes
```
- Switch branches or perform other tasks  
- Reapply the changes with:  
```bash
git stash pop # Reapply the stashed changes and remove them from the stash
```
```

## Module 6: Advanced Practices
### Concepts Covered:

- .gitignore patterns

- Tagging releases

- Rebasing vs. merging

```bash
CLI Commands:

bash
# .gitignore patterns
*.log
temp/
git tag v1.0                  # Release tagging
git rebase main               # Reapply commits on updated base
git cherry-pick <commit>      # Grab specific commit
```
