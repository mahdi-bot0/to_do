# Todo List App

A user-friendly todo list application with folder organization, checklist functionality, and due dates. Built with vanilla HTML/CSS/JavaScript for local static use.

**Live Demo:** https://mahdi-bot0.github.io/to_do/

## Features

- 📁 **Folder Organization**: Create multiple folders to organize your todos
- ✅ **Task Management**: Add, check, and delete checklist items
- 📅 **Due Dates**: Set due dates with visual urgency indicators (overdue/upcoming)
- 🎯 **Priority Levels**: High/medium/low priorities with color-coded badges
- 🏷️ **Custom Tags**: Add and filter tasks by custom tags/labels
- 📝 **Task Notes**: Add detailed descriptions and notes to any task
- 🔍 **Global Search**: Search across all tasks in all folders
- 🎨 **Filter & Sort**: Filter by priority or tag, sort by priority or due date
- 🌙 **Dark Mode**: Toggle between light and dark themes with persistence
- 📥 **Export/Import**: Backup and restore your data as JSON files
- 💾 **Auto-Save**: All data persists in browser localStorage
- 📱 **Responsive Design**: Works perfectly on mobile and desktop
- 🚀 **No Dependencies**: Pure HTML/CSS/JavaScript - just open and use
- 🤖 **Claude CLI Integration**: All features built using Claude Code CLI
- ⚡ **GitHub Actions**: Auto-deployment on every push

## Creating a New Website from Scratch

Follow these steps to create and deploy a brand new website project:

### Step-by-Step Guide

#### 1. Create Project Directory
```bash
# Create and navigate to your project folder
mkdir my-new-website
cd my-new-website
```

#### 2. Create Your HTML File
```bash
# Create a basic index.html file
touch index.html
```

Then open `index.html` in your editor and add your website content. Here's a minimal starter:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My New Website</title>
    <style>
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }
    </style>
</head>
<body>
    <h1>Welcome to My Website</h1>
    <p>This is my new website!</p>
</body>
</html>
```

#### 3. Initialize Git Repository
```bash
# Initialize git
git init

# Create .gitignore file
echo ".DS_Store" > .gitignore
```

#### 4. Set Up SSH Key (First Time Only)
If you haven't set up SSH keys for GitHub:

```bash
# Generate SSH key
ssh-keygen -t ed25519 -C "your_email@example.com" -f ~/.ssh/id_ed25519

# Start SSH agent
eval "$(ssh-agent -s)"

# Add key to agent
ssh-add ~/.ssh/id_ed25519

# Display public key (copy this)
cat ~/.ssh/id_ed25519.pub
```

Then add the key to GitHub:
1. Go to https://github.com/settings/keys
2. Click "New SSH key"
3. Paste your public key and save

Test the connection:
```bash
ssh -T git@github.com
```

#### 5. Create Initial Commit
```bash
# Stage your files
git add .

# Create first commit
git commit -m "Initial commit: Create new website"
```

#### 6. Create GitHub Repository
```bash
# Option A: Using GitHub CLI (recommended)
gh repo create my-new-website --public --source=. --remote=origin --push

# Option B: Manually via web browser
# 1. Go to https://github.com/new
# 2. Create repository named "my-new-website"
# 3. Don't initialize with README
# 4. Then run:
git remote add origin git@github.com:YOUR_USERNAME/my-new-website.git
git branch -M main
git push -u origin main
```

#### 7. Set Up GitHub Pages Auto-Deployment

Create the workflow file:
```bash
mkdir -p .github/workflows
```

Create `.github/workflows/deploy.yml` with this content:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Pages
        uses: actions/configure-pages@v4

      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: '.'

      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

Commit and push the workflow:
```bash
git add .github/workflows/deploy.yml
git commit -m "Add GitHub Pages deployment workflow"
git push
```

#### 8. Enable GitHub Pages

1. Go to your repo: `https://github.com/YOUR_USERNAME/my-new-website/settings/pages`
2. Under "Build and deployment"
3. Set **Source** to **"GitHub Actions"**
4. Save

#### 9. Wait for Deployment

1. Go to Actions tab: `https://github.com/YOUR_USERNAME/my-new-website/actions`
2. Watch the workflow run (takes 1-2 minutes)
3. Your site will be live at: `https://YOUR_USERNAME.github.io/my-new-website/`

#### 10. Start Developing with Claude CLI

Now you can use Claude Code CLI to add features:

```bash
# Example: Ask Claude to add a feature
# "Add a navigation menu with Home, About, and Contact sections"
# "Add a dark mode toggle"
# "Create a contact form"
```

Claude will:
- Read your code
- Implement the feature
- Create commits with proper messages
- Push changes (which auto-deploy via GitHub Actions)

### Quick Summary

For subsequent projects, the process is:

```bash
# 1. Create project
mkdir my-project && cd my-project
touch index.html

# 2. Add your HTML content (edit index.html)

# 3. Initialize git
git init
echo ".DS_Store" > .gitignore
git add .
git commit -m "Initial commit"

# 4. Create GitHub repo and push
gh repo create my-project --public --source=. --remote=origin --push

# 5. Add deploy workflow (copy from this repo)
mkdir -p .github/workflows
# Copy deploy.yml from this repo to .github/workflows/
git add .github/workflows/deploy.yml
git commit -m "Add GitHub Pages deployment"
git push

# 6. Enable GitHub Pages (set source to "GitHub Actions")
# Visit: https://github.com/YOUR_USERNAME/my-project/settings/pages

# 7. Start developing with Claude CLI!
```

---

## About This Project

This is a todo list application demonstrating the workflow described above.

## Setting Up This Specific Project

If you want to recreate THIS todo list app specifically, follow these detailed steps:

### 1. Initialize Git Repository

```bash
git init
```

### 2. Create SSH Key (if you don't have one)

```bash
# Generate SSH key
ssh-keygen -t ed25519 -C "your_email@example.com" -f ~/.ssh/id_ed25519 -N ""

# Start SSH agent and add key
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

# Display your public key
cat ~/.ssh/id_ed25519.pub
```

### 3. Add SSH Key to GitHub

1. Copy the output from `cat ~/.ssh/id_ed25519.pub`
2. Go to https://github.com/settings/keys
3. Click **"New SSH key"**
4. Paste your key and save

### 4. Test SSH Connection

```bash
ssh -T git@github.com
```

You should see: `Hi username! You've successfully authenticated...`

### 5. Create Initial Commit

```bash
# Stage files
git add .gitignore index.html

# Create initial commit
git commit -m "Initial commit: Add todo list app

Created a user-friendly todo list application with folder organization and checklist functionality. Built with vanilla HTML/CSS/JavaScript for local static use.

Co-Authored-By: Claude Sonnet 4.5 <noreply@anthropic.com>"
```

### 6. Create GitHub Repository

1. Go to https://github.com/new
2. Create a new repository (e.g., "to_do")
3. **Don't** initialize with README, .gitignore, or license

### 7. Connect to GitHub and Push

```bash
# Add remote (replace YOUR_USERNAME and YOUR_REPO with your details)
git remote add origin git@github.com:YOUR_USERNAME/YOUR_REPO.git

# Push to GitHub
git push -u origin main
```

### 8. Set Up GitHub Pages Workflow

The `.github/workflows/deploy.yml` file is already included in this repository.

```bash
# The workflow file should already be committed
# If not, add and commit it:
git add .github/workflows/deploy.yml
git commit -m "Add GitHub Pages deployment workflow"
git push
```

### 9. Enable GitHub Pages

1. Go to your repository settings: `https://github.com/YOUR_USERNAME/YOUR_REPO/settings/pages`
2. Under "Build and deployment"
3. Set **Source** to **"GitHub Actions"**
4. Save

### 10. Wait for Deployment

1. Go to the Actions tab: `https://github.com/YOUR_USERNAME/YOUR_REPO/actions`
2. Wait for the workflow to complete (1-2 minutes)
3. Your app will be live at: `https://YOUR_USERNAME.github.io/YOUR_REPO/`

## GitHub CLI Setup

Install and configure GitHub CLI for easier repository management:

### 1. Install GitHub CLI

**macOS (using Homebrew):**
```bash
brew install gh
```

**Windows (using winget):**
```bash
winget install --id GitHub.cli
```

**Linux (Debian/Ubuntu):**
```bash
sudo apt install gh
```

### 2. Authenticate GitHub CLI

```bash
gh auth login
```

Follow the prompts:
1. Select "GitHub.com"
2. Select "HTTPS" or "SSH" (SSH recommended if already set up)
3. Authenticate via web browser
4. Copy and paste the one-time code when prompted

### 3. Verify Authentication

```bash
gh auth status
```

You should see confirmation that you're logged in.

## Development Workflow with Claude CLI

This project uses Claude Code CLI for rapid feature development:

### Recommended Workflow

1. **Create GitHub Issue**
   ```bash
   gh issue create --title "Feature name" --body "Description"
   ```

2. **Work with Claude CLI**
   - Use Claude Code in your terminal/IDE
   - Reference the issue: "Implement feature from issue #X"
   - Claude will read code, implement changes, and create commits

3. **Review and Merge**
   ```bash
   gh pr create --title "..." --body "Closes #X"
   gh pr merge --squash
   ```

### Example Session

```bash
# Create issue
gh issue create --title "Add dark mode" --body "Toggle between light/dark themes"

# In Claude CLI session:
# "Implement dark mode feature from issue #X"
# Claude reads index.html, implements the feature, commits changes

# Create and merge PR
gh pr create --title "Add dark mode toggle" --body "Closes #X"
gh pr merge --squash
```

### Benefits of CLI Workflow

✅ **Fast**: Features implemented in 2-3 minutes
✅ **Reliable**: Direct file access and git operations
✅ **Flexible**: Full conversation context for complex changes
✅ **Tested**: Every feature in this repo built this way

### Alternative: GitHub Actions (Experimental)

Basic GitHub Actions integration exists for simple notifications:
- Workflow triggers on `@claude` mentions in issues
- Currently posts acknowledgment comments
- Full automation implementation in progress

## Project Structure

```
to_do/
├── .github/
│   └── workflows/
│       ├── deploy.yml            # GitHub Actions: Auto-deploy to Pages
│       └── claude-assistant.yml  # GitHub Actions: Claude AI integration
├── .gitignore                    # Git ignore file
├── index.html                    # Main application file (HTML + CSS + JS)
└── README.md                     # This file
```

## Local Development

To run locally, simply open `index.html` in your web browser:

```bash
open index.html
```

Or double-click the file in your file manager.

## Development Workflow

### Option 1: Manual Development

After making changes to the app:

```bash
# Stage your changes
git add .

# Commit with a descriptive message
git commit -m "Your commit message"

# Push to GitHub (triggers auto-deployment)
git push
```

The GitHub Actions workflow will automatically deploy your changes to GitHub Pages.

### Option 2: GitHub Issues + Claude CLI (Recommended)

The fastest way to add features - using GitHub CLI + Claude Code:

```bash
# 1. Create an issue
gh issue create --title "Add search feature" --body "Search tasks by keyword"

# 2. Use Claude CLI to implement
# In your Claude Code session, say:
# "Implement the search feature from issue #X"

# 3. Claude will:
#    - Read current code
#    - Implement the feature
#    - Create branch and commit
#    - Push changes

# 4. Create and merge PR
gh pr create --title "Add search feature" --body "Closes #X"
gh pr merge --squash
```

**This is how all features in this repo were built:**
- Due dates feature
- Priority levels
- Filter/sort functionality
- Footer with timestamp

**Time per feature:** 2-5 minutes from issue to live deployment

## Useful GitHub CLI Commands

```bash
# Repository
gh repo view                    # View repository details
gh repo view --web             # Open repository in browser

# Issues
gh issue list                  # List all issues
gh issue view 123              # View issue #123
gh issue create                # Create new issue
gh issue close 123             # Close issue #123
gh issue comment 123 --body "Comment text"

# Pull Requests
gh pr list                     # List all PRs
gh pr view 123                 # View PR #123
gh pr create                   # Create new PR
gh pr merge 123 --squash       # Merge PR with squash
gh pr checks                   # View PR checks status

# Actions/Workflows
gh workflow list               # List workflows
gh run list                    # List workflow runs
gh run view                    # View latest run details

# Secrets (for Claude API key)
gh secret list                 # List repository secrets
gh secret set SECRET_NAME      # Add a secret
```

## How It Works

- **Frontend Only**: No backend or database required
- **localStorage**: All data is saved in your browser's localStorage
- **Static Deployment**: Hosted on GitHub Pages as static files
- **Auto-Deploy**: Every push to `main` triggers automatic deployment
- **AI Integration**: Claude responds to GitHub comments via GitHub Actions

## Technologies Used

- HTML5
- CSS3 (with CSS Grid and Flexbox)
- Vanilla JavaScript (ES6+)
- GitHub Actions
- GitHub Pages

## Browser Compatibility

Works on all modern browsers that support:
- localStorage
- ES6 JavaScript
- CSS Grid and Flexbox

## License

Feel free to use and modify this project as needed.

## Troubleshooting

### SSH Authentication Issues

If you get "Permission denied" errors:
```bash
# Check if SSH key is added to agent
ssh-add -l

# If not, add it
ssh-add ~/.ssh/id_ed25519
```

### GitHub CLI Not Working

If `gh` command is not found:
```bash
# macOS: Reinstall via Homebrew
brew install gh

# Verify installation
which gh

# Re-authenticate if needed
gh auth login
```

### GitHub Pages Not Deploying

1. Verify Pages is enabled with "GitHub Actions" as source
2. Check Actions tab for error messages
3. Ensure workflow has proper permissions in repository settings
4. Check workflow file exists: `.github/workflows/deploy.yml`

### Claude Not Responding to Comments

If Claude doesn't respond when mentioned:

1. **Check API Key is set:**
   ```bash
   gh secret list
   ```
   Should show `ANTHROPIC_API_KEY`

2. **Verify workflow exists:**
   - Check `.github/workflows/claude-assistant.yml` exists
   - View in repo: `https://github.com/YOUR_USERNAME/YOUR_REPO/blob/main/.github/workflows/claude-assistant.yml`

3. **Check workflow run:**
   ```bash
   gh run list --workflow=claude-assistant.yml
   ```
   View the latest run for error messages

4. **Ensure proper mention:**
   - Use `@claude` (lowercase) in comments
   - Comment must be on an issue, not a PR description

5. **Check API key validity:**
   - Visit: https://console.anthropic.com/settings/keys
   - Verify key is active
   - If expired, create new key and update secret:
     ```bash
     gh secret set ANTHROPIC_API_KEY
     ```

6. **Check workflow permissions:**
   - Go to: `Settings` → `Actions` → `General`
   - Under "Workflow permissions", ensure "Read and write permissions" is enabled

### Local Changes Not Showing

If localStorage data seems stuck:
- Clear browser cache and localStorage
- Open browser DevTools > Application > Local Storage > Clear

### Date Showing Incorrectly

If dates display one day earlier than selected:
- This was fixed in a previous update
- Ensure you're running the latest version
- Clear browser cache and reload
