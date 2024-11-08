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

   - Press `Enter` to accept the default location, and set a passphrase for extra security.

2. **Add the SSH Key to GitHub**:
   - Open the key file by running `cat ~/.ssh/id_ed25519.pub` in **Terminal** (or **Git Bash** for Windows users) to display the SSH public key.
   - Copy the whole row given as output when running the command above.
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
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

- `user_name`: Sets the name that will appear in your commits.
- `user_email`: Sets the email that will appear in your commits. <br>
  (use the same email as on GitHub for consistency).

You can verify your configuration by running:

```bash
git config --list
```

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

- **Add Files to Staging**:

  ```bash
  git add .
  ```

- **Commit Changes**:

  ```bash
  git commit -m "Commit message"
  ```

- **Push Changes to GitHub**:

  ```bash
  git push origin main
  ```

- **Pull Changes from GitHub**:

  ```bash
  git pull origin main
  ```

- **Create a Branch** (for features or specific tasks):

  ```bash
  git checkout -b branch-name
  ```

- **Merge a Branch**:

  ```bash
  git merge branch-name
  ```

---

## Additional Resources

- [GitHub Documentation: Getting started with GitHub](https://docs.github.com/en/get-started)
- [Git Basics: Pro Git Book](https://git-scm.com/book/en/v2)
- [GitHub SSH Guide: Connecting to GitHub with SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

---
