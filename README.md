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
CLI Commands:
git init
git status
git add <file>            # Stage specific file
git add .                 # Stage all changes
git commit -m "Message"
git log
git diff
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
mkdir my-first-git-repo
cd my-first-git-repo
```

2. Initialize Git repo

```bash
git init
```

3. Create README.md and write something

```bash
code README.md
```

4. Stage & commit

```bash
git add README.md
git commit -m "My first commit"
```

5. Check Log

```bash
git log
```

6. Modify README.md then check status & diff

```bash
git status
git diff
```
7. Stage, commit all changes and check log

```bash
git add .
git commit -m "<message>"
git log
```

## Module 2: Branching & Merging
### Concepts Covered:

- Branch isolation

- Fast-forward vs. 3-way merges

- Conflict resolution

```bash
CLI Commands:

bash
git branch                       # List branches
git branch <name>                # Create branch
git switch <branch>              # Switch branch
git switch -c <new-branch>       # Create & switch
git merge <branch>               # Merge into current branch
```

### Exercise:

1. Create feature branch from main

2. Make conflicting changes in both branches

3. Resolve merge conflict manually:

3. Edit conflicted files

4. git add resolved files

5. git commit

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

1. Create GitHub repo (no README/license)
Create an account on GitHub
Initialize a repository 
    
2. Connect local repo to GitHub
reference: https://docs.github.com/en/authentication/connecting-to-github-with-ssh
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```
Enter file in which to save the key (/c/Users/YOU/.ssh/id_ALGORITHM):[Press enter]
```bash
clip < ~/.ssh/id_ed25519.pub
```
In the upper-right corner of any page on GitHub, click your profile picture, then click  Settings.

In the left sidebar: Access > SSH and GPG keys

Click New SSH key or Add SSH key.

In the "Title" field, add a descriptive label for the new key.

In the "Key" field, paste what was copied from the clip command

Click Add SSH key.

```bash
git remote add origin git@github.com:YourUsername/YourRepository.git
```
4. Push branches
```bash
git push -u origin main
```
If your local branch is named master, use:
```bash
git push -u origin master
```
5. Clone a partner's repo
```bash
git clone git@github.com:partnerusername/their-repo-name.git
```   

## Module 4: Collaboration Workflow

### Concepts Covered:

- Forking a repository on GitHub
- Cloning the forked repository
- Creating a new branch for changes
- Making and committing changes in the cloned repo
- Pushing changes to the forked GitHub repo
- Opening a Pull Request (PR)

---

Task:
There is a base repository with a folder named 'A'. The task is to add a .md (README) file in folder 'A', push it, and open a Pull Request to contribute it.

### CLI Commands:

bash
git clone <your-fork-url>            # Clone your forked repo
git switch -c <your-branch-name>     # Create and switch to a new branch
cd A                                 # Navigate to folder A
git add <file>                       # Stage your changes
git commit -m "Your message"         # Commit the changes
git push origin <your-branch-name>   # Push your branch to your GitHub fork


---

### Exercise:

#### 1. Fork the Original Repository

- Go to the GitHub page of the repository you want to contribute to.
- Click on the *Fork* button in the upper-right corner.
- This will create a copy of the repository under your GitHub account.


#### 2. Clone the Forked Repository

bash
git clone https://github.com/your-username/forked-repo.git
cd forked-repo


#### 3. Create and Switch to a New Branch

bash
git switch -c my-feature-branch

> This keeps your changes isolated from the main code.


#### 4. Navigate to folder A

bash
cd A

> This will navigate to folder A, residing inside the base repository.


#### 5. Make Changes

- Edit files, fix bugs, or add features.
- Save your work.


#### 6. Stage and Commit Changes

bash
git add .
git commit -m "Add a meaningful commit message describing your change"


#### 7. Push Your Branch to Your Fork

bash
git push origin my-feature-branch


#### 8. Open a Pull Request (PR)

- Go to your forked repository on GitHub.
- You'll see a prompt to open a pull request for the pushed branch.
- Click *"Compare & pull request"*.
- Add a title and description for your changes.
- Click *"Create pull request"*.

> Now the project maintainers can review and merge your contributions!

---

### ✅ Summary:

- Fork → Clone → Branch → Navigate → Change → Push → PR
- Contribute to open source without affecting the original code directly.


## Module 5: Undoing Changes
### Concepts Covered:

- Commit history rewriting

- Stashing temporary work

```bash
CLI Commands:

bash
git restore <file>              # Discard uncommitted changes
git reset --soft HEAD~1         # Undo commit (keep changes)
git reset --hard HEAD~1         # ⚠️ Destroy last commit
git revert <commit-hash>        # Safe undo for shared history
git stash                       # Temporary shelf
```

### Exercise:

1. Commit → git reset --soft → modify → recommit

2. Intentionally break code → git restore

3. Use git revert on pushed commit

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
