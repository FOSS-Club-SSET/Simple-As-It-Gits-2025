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

### Why collaborate on GitHub?

- Because coding alone is like talking to yourself — sometimes genius, sometimes chaos.  
- Working as a **team** on a shared codebase helps build real-world dev skills.
- GitHub is like a **Google Drive for your code**, but way more powerful for teams.

> Think of GitHub like a giant project notebook in the cloud.  
> You and your friends each write your parts (on different pages a.k.a. branches), then submit them (via Pull Requests), and review changes together.

---

### Concepts Covered:

- Forking and Cloning other people's repositories
- Making your changes and **pushing** them online
- Collaborating with Pull Requests (PRs)
- Syncing with remote changes using `fetch`, `pull`, and `rebase`
- Understanding what "Upstream" means

---

### CLI Commands:

```bash
git fetch                         # Get updates from remote without merging
git pull                          # Fetch + merge remote changes
git pull --rebase                 # Reapply your changes on top of latest
git push                          # Push your local changes to remote
git push --force-with-lease       # Safe force-push (used with rebase)
git remote -v                     # View remote URLs
```

---

### Real-World Analogy

> Imagine you're all editing a group project:  
> - GitHub = shared folder  
> - You = edit your own copy (branch)  
> - PR = "Hey team, check and merge my part"  
> - Merge conflict = “Oops! We both wrote on the same paragraph.”

---

### Exercise: Simulate Team Collaboration

Let’s pretend you're collaborating with a teammate named `Alex`. You both are working on the same project repo.

---

#### Step 1: One person pushes a new change to the remote

Let’s say *Alex* pushes a new commit to GitHub from their local:

```bash
git add alex-feature.txt
git commit -m "Alex adds a new feature"
git push origin main
```

---

#### Step 2: You fetch Alex’s changes into your local repo

Back on your local machine:

```bash
git fetch origin                # Gets the latest changes from GitHub
git merge origin/main          # Merge those changes into your current branch
```

Or, alternatively (more modern and clean):

```bash
git pull --rebase              # Reapply your work on top of latest remote work
```

> Rebase helps keep the history clean.  
> It’s like saying: "Let me add my story **after** Alex’s instead of **merging side by side**."

---

#### Step 3: Push your updated work to GitHub

```bash
git push origin main
```

---

#### Step 4: Simulate a Pull Request (PR)

Go to your GitHub repository in the browser:

1. Click on “Pull Requests” tab  
2. Click “New Pull Request”  
3. Compare your feature branch with `main`  
4. Click **Create Pull Request**  
5. Add a meaningful title and description

> This is how real-world teams review code.  
> Think of PRs as "code homework submissions" — your teammates will give feedback before it's merged.

---

#### Step 5: Resolve Merge Conflicts (if any)

If someone else modified the same lines as you, GitHub or CLI will throw a **merge conflict**.

To fix it:

1. Open the conflicting file  
2. You'll see something like:

```txt
<<<<<<< HEAD
This is your change
=======
This is Alex's change
>>>>>>> main
```

3. Edit to combine changes like this:

```txt
This is your change
This is Alex's change
```

4. Stage and commit resolved file:

```bash
git add conflicted-file.txt
git commit -m "Resolve conflict between Alex and my changes"
```

---

#### Step 6: (Optional) Push with Force

If you rebased your changes:

```bash
git push --force-with-lease
```

> It’s safer than `--force`, and checks if someone else pushed since your last pull.

---

#### Bonus: Upstream? What’s that?

If you fork someone’s repo, their repo is your **upstream**.

You can sync with it like this:

```bash
git remote add upstream git@github.com:OriginalUser/OriginalRepo.git
git fetch upstream
git merge upstream/main
```

> It's like saying: "Let me pull updates from the original project I forked from."

---

### Collaboration Wisdom 💡

- Always **pull before you push**
- Use `pull --rebase` if working solo, `merge` if working with teammates
- Don’t be afraid of merge conflicts — they’re part of the dev life
- Communicate on PRs and commit messages like a pro

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
git reset --hard HEAD~1         # ⚠️ Destroy last commit
git revert <commit-hash>        # Safe undo for shared history
git stash                       # Temporary shelf
```

### Exercise:

1. Undo and recommit
-Make a change and commit it
```bash
git reset --soft HEAD~1
```
-Modify the file and recommit the updated change

2. Discard Broken Code
-intentionally break a file
-Discard changes with:
```bash
git restore <file>
```

3. Revert a pushed commit
-Identify the hash of a commit already pushed
```bash
git revert <commit-hash>
```
-Push the reverted commit to remote
```bash
git push
```

4. Use git stash
-Make uncommitted changes
```bash
git stash
```
-switch branches of perform other tasks
-reapply the changes with:
```bash
git stash pop
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
