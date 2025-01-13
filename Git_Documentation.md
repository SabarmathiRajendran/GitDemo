# 1. Git Basics

To set up your Git configuration for GitHub on your local machine, you need to configure your user name and email. This ensures your commits are properly attributed to your GitHub account.

**Command to Set Git Configuration:**
- Set your Git username: `git config --global user.name "Your GitHub Username"`
- Set your Git email: `git config --global user.email "your-email@example.com"`
- Verify the configuration: `git config --global --list`

The --global flag sets the configuration for all repositories on your local machine. To configure it for a specific repository, run the command without --global inside that repository.

## 1.1 git init

Initializes a new Git repository in the current directory.
- Command: `git init`
- Example:
    - `mkdir my_project`
    - `cd my_project`
    - `git init`

Creates a new Git repository in my_project.

## 1.2 git clone

Clones an existing repository from a remote source to your local machine.
- Command: `git clone <repository-url>`
- Example: `git clone https://github.com/username/repo.git`

Clones the repository from the given URL.

## 1.3 git status

Shows the status of your working directory and staging area.
- Command: `git status`
- Example: `git status`

Displays untracked, modified, and staged files.

# 2. Staging and Committing Changes

## 2.1 git add

Stages changes for the next commit.
- Command: `git add <file>`
- Example: `git add index.html`

Stages index.html for committing.

- To stage all files: `git add .`

## 2.2 git commit

Records changes to the local repository.
- Command: `git commit -m "<message>"`
- Example: `git commit -m "Initial commit"`

Commits the staged changes with the message "Initial commit".

**Stages and commits all modified files in one command:**

- Command: `git commit -am "<message>"`
- Example: `git commit -am "Updated index.html"`

Stages and commits all modified files with the message "Updated index.html".

# 3. Branching
## 3.1 git branch
**Lists Branches:** Lists all branches in the repository.
- Command: `git branch`
- Example: `git branch`

**Create a Branch:** Creates a new branch named feature-branch.
- Command: `git branch <branch-name>`
- Example: `git branch feature-branch`

**Delete a Branch:** Deletes the feature-branch.
- Command: `git branch -d <branch-name>`
- Example: `git branch -d feature-branch`

**Rename the Current Branch:** Renames the current branch to the specified name.
- Command: git branch -m <new-branch-name>
- Example: git branch -m feature-branch

**Rename a Different Branch:** Renames a branch that you are not currently on.
- Command: `git branch -m <old-branch-name> <new-branch-name>`
- Example: `git branch -m old-branch feature-branch`

## 3.2 git checkout
**Creates a new branch and switches to it.**
- Command: `git checkout -b <new-branch>`
- Example: `git checkout -b feature-branch`

Creates and switches to feature-branch.

**Switches to an existing branch.**

- Command: `git checkout <branch>`
- Example: `git checkout main`

Switches to main.

# 4. Connecting to a Remote Repository**

**Viewing Remote Repositories:** Displays the URLs of remote repositories associated with your local repository (both fetch and push URLs).
- Command: `git remote -v`

**Adding a Remote Repository:** Adds a new remote repository to your local repository.
- Command: `git remote add <name> <url>`
- Example: `git remote add origin https://github.com/user/repository.git`

# 5. Pushing and Pulling Changes

## 5.1 git push

Uploads local repository content to a remote repository.
- Command: `git push <remote> <branch>`
- Example: `git push origin main`

Pushes the main branch to the origin remote.

**Using Personal Access Token (PAT) for Authentication:**

When pushing to a remote repository, Git will prompt you for your GitHub username and password. Instead of using your GitHub password, you will use your Personal Access Token (PAT).

- **Username for 'https://github.com': `Enter your GitHub Username`**

- **Password for 'https://YourUsername@github.com': `Paste your Personal Access Token (PAT) here (not your GitHub password)`**

**Note:** You can generate a PAT by following the instructions in yout GitHub
`GitHub settings -> Developer settings → Personal access tokens -> Token (classic) -> Generate new token -> Provide a Note for the token -> Select Expiration Duration -> Select scopes -> Click Generate Token.

*A Personal Access Token (PAT) can only be **viewed once upon generation; you must copy it immediately**, and if lost, a new token must be created, requiring you to update your Git configuration or re-enter it when prompted for authentication.*

## 5.2 git pull

**5.2.1 Pull Request**

A request to merge changes from one branch (e.g., feature-branch) into another (e.g., main).

Commonly used in collaborative projects for:

- Reviewing code before merging.
- Discussing changes with team members.
- Tracking progress and issues.

**5.2.2 Prerequisites**

Ensure changes are committed and pushed to a remote branch.
Example: `git push origin feature-branch`

**5.2.3 Creating a Pull Request on GitHub**

- **Go to the Repository:** Open your GitHub repository in a browser.
- **Navigate to Pull Requests:** Click the Pull Requests tab.
- **Create New Pull Request:**
    - Click New Pull Request.
    - Select:
        - **Base branch:** The branch you want to merge changes into (e.g., main).
        - **Compare branch:** The branch with your changes (e.g., feature-branch).
- **Review Changes:** GitHub displays a comparison of the changes between branches.
- **Add Details:**
    - Enter a descriptive title and summary of the changes.
    - Optionally, link issues (e.g., Closes #123) or tag reviewers.
- **Submit the Pull Request:** Click Create Pull Request.

**5.2.4 Reviewing a Pull Request**

A review has three possible statuses:

- **Comment:** Submit general feedback without explicitly approving the changes or requesting additional changes.
- **Approve:** Submit feedback and approve merging the changes proposed in the pull request.
- **Request changes:** Submit feedback that must be addressed before the pull request can be merged.

**5.2.5 Merging a Pull Request**
- **Navigate to the Pull Request:**
    - Go to the repository on GitHub.
    - Click on the Pull Requests tab.
    - Select the pull request you want to merge.
- **Review the Changes:**
    - Scroll through the Files changed tab to review the modifications.
    - Use the Conversation tab to review comments, approvals, or any unresolved conflicts.
- **Choose a Merge Option:**
    - At the bottom of the pull request, you’ll see a Merge pull request button with a dropdown arrow next to it.
    - Click the dropdown arrow to view the available options:
        - **Create a merge commit:** Default option, merges with a merge commit.
        - **Squash and merge:** Combines all commits into one before merging.
        - **Rebase and merge:** Rebases commits from the branch onto the base branch without a merge commit.
- **Select and Confirm the Merge Option:**
    - Choose the desired merge option.
    - If necessary, edit the commit message (e.g., for squashing).
    - Click Confirm merge to complete the process.
- **Verify the Merge:**
    - Go to the Commits or Code tab of the repository to confirm that the changes were merged.

# 6. Viewing History
## 6.1 git log

Displays the commit history.
- Command: `git log`
- Example: `git log --oneline`

Shows a condensed log of commits.

## 6.2 git diff

Displays changes between the working directory and the staging area.

- Command: `git diff`
- Example: `git diff`

Shows modifications not yet staged for commit.

## 6.2 git diff HEAD

Displays changes between the working directory and the latest commit.

- Command: `git diff HEAD`
- Example: `git diff HEAD`

Shows all changes made since the last commit.