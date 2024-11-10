# Git and GitHub Setup Guide for Collaborative Projects

This guide covers the basics of setting up Git, creating a GitHub repository for collaborative work, configuring SSH for authentication, and using essential Git commands.

---

## Table of Contents

- [Git and GitHub Setup Guide for Collaborative Projects](#git-and-github-setup-guide-for-collaborative-projects)
  - [Table of Contents](#table-of-contents)
  - [Introduction to Git and GitHub](#introduction-to-git-and-github)
  - [Installing Git](#installing-git)
    - [For Windows](#for-windows)
    - [For macOS](#for-macos)
  - [Setting Up SSH Authentication](#setting-up-ssh-authentication)
    - [Step-by-Step SSH Setup](#step-by-step-ssh-setup)
  - [Configuring Git](#configuring-git)
  - [Creating a GitHub Repository](#creating-a-github-repository)
  - [Essential Git Commands](#essential-git-commands)
  - [Typical Example Workflow](#typical-example-workflow)
    - [Step 1: Clone the Repository](#step-1-clone-the-repository)
    - [Step 2: Create a New Branch](#step-2-create-a-new-branch)
    - [Step 3: Make Changes](#step-3-make-changes)
    - [Step 4: Add Files to Staging](#step-4-add-files-to-staging)
    - [Step 5: Commit Your Changes](#step-5-commit-your-changes)
    - [Step 6: Push Your Branch to GitHub](#step-6-push-your-branch-to-github)
    - [Step 7: Create a Pull Request](#step-7-create-a-pull-request)
    - [Step 8: Merge the Pull Request](#step-8-merge-the-pull-request)
    - [Step 9: Update Your Local main Branch](#step-9-update-your-local-main-branch)
    - [Step 10: Clean Up](#step-10-clean-up)
  - [Additional Tips](#additional-tips)
  - [Additional Resources](#additional-resources)

---

## Introduction to Git and GitHub

**Git** is a version control system that allows you to track changes to your code over time, manage versions, and collaborate with others. **GitHub** is a cloud-based platform that hosts Git repositories, making it easy to share, collaborate, and manage projects with others.

---

## Installing Git

### For Windows

1. Download Git from the official [Git website](https://git-scm.com/).
2. Run the installer and follow the setup instructions.
   - For most options, you can use the default settings.
   - Make sure to choose "Git from the command line and also from third-party software" for better integration.
3. After installation, verify Git by opening **Git Bash** and running:

   ```bash
   git --version
   ```

### For macOS

Most macOS systems come with Git pre-installed. To check, open **Terminal** and type:

```bash
git --version
```

If Git isn’t installed, you can install it by downloading from the [Git website](https://git-scm.com/) and running the installer.

---

## Setting Up SSH Authentication

To connect to GitHub securely, you can set up SSH authentication. This is a “set it and forget it” method that establishes a secure, device-specific connection to GitHub.

### Step-by-Step SSH Setup

1. **Generate an SSH Key**:
   - In your terminal, run:

     ```bash
     ssh-keygen -t ed25519 -C "your.email@example.com"
     ```

     (Here, ed25519 is the algorithm used to generate a personal SSH key.)

   - Press `Enter` to accept the default location, and optionally set a passphrase for extra security.

2. **Add the SSH Key to GitHub**:
   - Open the key file by running `cat ~/.ssh/id_ed25519.pub` in **Terminal** (or **Git Bash** for Windows users) to display the SSH public key.
   - Log in to GitHub, go to **Settings** > **SSH and GPG keys** > **New SSH key**.
   - Paste the key into the **Key** field and give it a descriptive title like "My Laptop".
   - [GitHub's guide on SSH setup](https://docs.github.com/en/authentication/connecting-to-github-with-ssh) provides more details.

3. **Test the SSH Connection**:
   - In your terminal, run:

     ```bash
     ssh -T git@github.com
     ```

   - Type `yes` if prompted to confirm the connection.
   - If successful, you’ll see a welcome message from GitHub.

---

## Configuring Git

Once Git is installed and SSH is set up, configure Git with your username and email. This information will be associated with your commits, making it clear who made each change.

```bash
git config --global user_name "Your Name"
git config --global user_email "your.email@example.com"
```
**If using `user_name` or `user_email`** : Try using `user.name` or `user.email`.

- `user_name`: Sets the name that will appear in your commits.
- `user_email`: Sets the email that will appear in your commits. <br>
  (use the same email as on GitHub for consistency).

You can verify your configuration by running:

```bash
git config --list
```

(Which prints out all your git config variables.)

---

## Creating a GitHub Repository

To create a shared repository for your group:

1. Go to **GitHub** and log in.
2. Click **New** under Repositories.
3. Give your repository a name (e.g., `group-labs`)
   - Set it as Public or Private
   - Optionally, check the box to add a README file. (This is where repository documentation, descriptions and guidelines are written.)
4. Click **Create repository**.

Once created, share the SSH URL with your collaborators so they can clone the repo:

1. Go to your repository on GitHub.
2. Click the **Code** button.
3. In the dropdown, select **SSH**.
4. Copy the SSH URL provided (it will look like `git@github.com:username/repository.git`).

---

## Essential Git Commands

These commands are essential for managing your project with Git:

- **Clone the Repository**:

  ```bash
  git clone git@github.com:username/repository.git
  ```
  
  *Creates a local copy of the remote repository from GitHub to your machine. This includes all the project's files, history, and branches.*

- **Add Files to Staging**:

  ```bash
  git add .
  ```

  *Adds all new or modified files in the current directory to the staging area. The staging area is where you prepare changes before committing them to the repository.*

- **Commit Changes**:

  ```bash
  git commit -m "Commit message"
  ```

  *Saves the changes added to the staging area into the repository's history with a descriptive message explaining what was done.*

- **Push Changes to GitHub**:

  ```bash
  git push origin main
  ```

  *Uploads your local commits in the main branch to the corresponding remote branch on GitHub, updating the remote repository with your changes.*

- **Pull Changes from GitHub**:

  ```bash
  git pull origin main
  ```

  *Fetches and merges updates from the remote main branch on GitHub into your local main branch, ensuring your local repository is up-to-date.*

- **Create a Branch** (for features or specific tasks):

  ```bash
  git checkout -b branch-name
  ```

  *Creates a new branch named branch-name and switches to it. Branches allow you to work on features or fixes separately from the main codebase*

- **Merge a Branch**:

  ```bash
  git merge branch-name
  ```

  *Integrates changes from branch-name into the current branch. This is typically done after completing work on a feature or fix.*

---

## Typical Example Workflow

Let's walk through a common scenario where you're collaborating on a project and want to add a new feature.

### Step 1: Clone the Repository

First, clone the repository to your local machine:

```bash
git clone git@github.com:username/repository.git
```

Navigate into the project directory:

```bash
cd repository
```

### Step 2: Create a New Branch

Create a new branch for the feature you're working on:

```bash
git checkout -b feature/new-login
```

This creates and switches you to a branch named feature/new-login.

### Step 3: Make Changes

Edit files and make changes related to your new feature.

### Step 4: Add Files to Staging

After making changes, add them to the staging area:
```bash
git add .
```

The `.` adds all changed files. Alternatively, specify files individually: git add filename.

### Step 5: Commit Your Changes

Commit the staged changes with a meaningful message:

```bash
git commit -m "Add new login feature"
```

### Step 6: Push Your Branch to GitHub

Push your new branch to the remote repository:

```bash
git push origin feature/new-login
```

This makes your branch available on GitHub for collaboration or review.

### Step 7: Create a Pull Request

On GitHub:

  1. Navigate to the repository.
  2. You’ll see a prompt to compare & pull request your recent push.
  3. Click on "Open Pull Request".
  4. Add a description and submit the pull request.
- This allows team members to review your code before merging.

### Step 8: Merge the Pull Request

After approval:

- Merge the pull request on GitHub, integrating your feature into the main branch.

### Step 9: Update Your Local main Branch

Switch back to the main branch locally and pull the latest changes:

```bash
git checkout main
git pull origin main
```

### Step 10: Clean Up

Delete the feature branch locally and remotely (optional):

```bash
git branch -d feature/new-login          # Deletes local branch
git push origin --delete feature/new-login  # Deletes remote branch
```

---

## Additional Tips

- Regularly Pull Updates:

  Before starting work and before pushing changes, it's good practice to pull updates to avoid conflicts:

```bash
git pull origin main
```

- Handling Merge Conflicts:
  
  If you encounter merge conflicts when pulling or merging, Git will indicate which files need attention. You'll need to manually resolve these conflicts in the affected files.

- View Branches:

List all branches:

```bash
git branch          # Local branches
git branch -a       # All branches including remote
```

- Switching Branches:

Switch to an existing branch:

```bash
git checkout branch-name
```

- Stashing Changes:

If you need to switch branches but have uncommitted changes:

```bash
git stash           # Saves changes for later
git stash pop       # Applies stashed changes
```

- Check Status:

See the status of your working directory and staging area:

```bash
git status
```

- Viewing Commit History:

View the commit history for the current branch:
```bash
git log
```

## Additional Resources

- [GitHub Documentation: Getting started with GitHub](https://docs.github.com/en/get-started)
- [Git Basics: Pro Git Book](https://git-scm.com/book/en/v2)
- [GitHub SSH Guide: Connecting to GitHub with SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

---
