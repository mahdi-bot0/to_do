# Todo List App

A user-friendly todo list application with folder organization, checklist functionality, and due dates. Built with vanilla HTML/CSS/JavaScript for local static use.

**Live Demo:** https://mahdi-bot0.github.io/to_do/

## Features

- 📁 Create multiple folders to organize your todos
- ✅ Add, check, and delete checklist items
- 📅 Set due dates for tasks with visual urgency indicators
- 💾 Persistent storage using localStorage
- 🎨 Clean, modern, responsive design
- 🚀 No dependencies - just open and use
- 🤖 Claude AI integration for automated development via GitHub comments

## Quick Start for New Projects

Here's the complete setup flow for creating a similar project from scratch:

1. **Git & SSH Setup** → Initialize repo, create SSH key, add to GitHub
2. **GitHub Repo** → Create repository, push initial code
3. **GitHub Pages** → Enable Pages with GitHub Actions source
4. **GitHub CLI** → Install `gh`, authenticate with `gh auth login`
5. **Claude Integration** → Get Anthropic API key, add to repository secrets
6. **Development** → Create issues, mention `@claude`, merge PRs

**See detailed instructions below for each step.**

## Setup Instructions

Follow these steps to set up this project from scratch:

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

## Claude AI Integration Setup

Enable Claude to automatically respond to GitHub issue comments and implement features:

### 1. Get Anthropic API Key

1. Visit: https://console.anthropic.com/settings/keys
2. Sign in or create an account
3. Click **"Create Key"**
4. Copy the API key (you won't be able to view it again)

### 2. Add API Key to Repository Secrets

1. Go to your repository settings: `https://github.com/YOUR_USERNAME/YOUR_REPO/settings/secrets/actions`
2. Click **"New repository secret"**
3. Enter:
   - Name: `ANTHROPIC_API_KEY`
   - Secret: (paste your API key)
4. Click **"Add secret"**

### 3. Verify Claude Workflow

The `.github/workflows/claude-assistant.yml` file should already be in your repository.

If not, ensure it's committed:
```bash
git add .github/workflows/claude-assistant.yml
git commit -m "Add Claude GitHub Actions integration"
git push
```

### 4. Using Claude via GitHub Comments

Once set up, you can interact with Claude directly from GitHub:

1. **Create an issue** or comment on an existing one
2. **Mention Claude** in your comment:
   ```
   @claude Can you work on this?
   ```
   or
   ```
   @claude Please implement this feature
   ```
3. **Claude will automatically:**
   - Respond to your comment within minutes
   - Analyze the issue
   - Implement requested features or fixes
   - Create branches and pull requests as needed

**Example Workflow:**
```markdown
Issue: Add search functionality

Comment: @claude Can you add a search feature to filter tasks?

Claude will:
1. Respond with implementation plan
2. Create a feature branch
3. Implement the search functionality
4. Create a pull request for review
```

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

### Option 2: GitHub Issues + GitHub CLI

Using GitHub CLI for feature development:

```bash
# Create an issue
gh issue create --title "Feature name" --body "Description"

# List open issues
gh issue list

# Create a branch from an issue
gh issue develop 123 --checkout

# Make your changes, then commit
git add .
git commit -m "Implement feature"

# Push and create PR
git push -u origin feature-branch
gh pr create --title "PR title" --body "Description"

# Merge PR when ready
gh pr merge 123 --squash
```

### Option 3: Claude AI Automation (Recommended)

The fastest way to add features:

1. **Create an issue on GitHub:**
   - Go to: `https://github.com/YOUR_USERNAME/YOUR_REPO/issues/new`
   - Describe the feature or bug

2. **Mention Claude in a comment:**
   ```
   @claude Can you implement this?
   ```

3. **Claude automatically:**
   - Analyzes the issue
   - Creates a feature branch
   - Implements the changes
   - Creates a pull request
   - Responds with a summary

4. **Review and merge:**
   ```bash
   # Via CLI
   gh pr merge PULL_NUMBER --squash

   # Or via GitHub web interface
   ```

5. **Changes auto-deploy** to GitHub Pages!

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
