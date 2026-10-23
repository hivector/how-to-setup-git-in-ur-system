# Git & GitHub Setup Guide

A beginner-friendly guide to installing Git, connecting GitHub to your terminal, and uploading your first project using command-line tools.

## 1. Install Git and GitHub CLI

Install Git and GitHub CLI using your system's package manager.

Verify the installations:

```bash
git --version
gh --version
```


## 2. Configure Git

Set your Git username and email address:

```bash
git config --global user.name "YOUR_USERNAME"
git config --global user.email "YOUR_EMAIL"
```

Check your configuration:

```bash
git config --global --list
```

**Tip:** If you have GitHub email privacy enabled, use your GitHub-provided `noreply` email from [GitHub Email Settings](https://github.com/settings/emails).

```bash
git config --global user.email "YOUR_NOREPLY_EMAIL"
```


## 3. Authenticate with GitHub

GitHub CLI simplifies authentication:

```bash
gh auth login
```

Follow the prompts to select GitHub.com, choose HTTPS, and authenticate through a web browser.

Verify your login:

```bash
gh auth status
```


## 4. Navigate to Your Project

Move into the directory containing your project:

```bash
cd /path/to/your/project
```

If a directory name contains spaces, enclose the path in quotation marks:

```bash
cd "/path/to/My Project"
```

Check your current directory and its contents:

```bash
pwd
ls -la
```


## 5. Initialize Git

Inside your project directory, run:

```bash
git init
```

Before uploading files, create a `.gitignore` file to exclude files that should not be tracked.

Example:

```gitignore
.env
.venv/
__pycache__/
node_modules/
```

Adapt it to your project's requirements. Never upload passwords, API keys, or private credentials.


## 6. Stage and Commit Your Files

Stage your files:

```bash
git add .
```

Review the staged changes:

```bash
git status
```

Create your first commit:

```bash
git commit -m "Initial commit"
```

A commit records a snapshot of the staged changes.


## 7. Create a GitHub Repository

After authenticating with GitHub CLI, create a private repository directly from your project directory:

```bash
gh repo create my-project --private --source=. --remote=origin --push
```

For a public repository, use:

```bash
gh repo create my-project --public --source=. --remote=origin --push
```

Replace `my-project` with your preferred repository name.

Alternatively, create an empty repository on [GitHub](https://github.com/new) and connect it manually:

```bash
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/my-project.git
git push -u origin main
```

Replace the placeholders with your GitHub username and repository name.

## 8. Upload Future Changes

Whenever you modify your project, use:

```bash
git add .
git commit -m "Describe your changes"
git push
```

You only need to create the repository once.



## 9. Useful Git Commands

| Command | Purpose |
|---|---|
| `git status` | Check repository changes |
| `git add .` | Stage changes in the current directory |
| `git add -A` | Stage additions, modifications, and deletions |
| `git commit -m "message"` | Create a commit |
| `git log --oneline` | View recent commits |
| `git remote -v` | View remote URLs |
| `git branch` | List local branches |
| `git pull --rebase origin main` | Integrate remote changes |
| `git push` | Upload commits |
| `git rev-parse --show-toplevel` | Find the repository root |

## Conclusion

The basic Git workflow is:

**Initialize → Stage → Commit → Push**

Once Git is configured and GitHub authentication is complete, you can manage your projects directly from the terminal without repeatedly uploading files through the GitHub website.
