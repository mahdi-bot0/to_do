# Todo List App

A user-friendly todo list application with folder organization and checklist functionality. Built with vanilla HTML/CSS/JavaScript for local static use.

**Live Demo:** https://mahdi-bot0.github.io/to_do/

## Features

- 📁 Create multiple folders to organize your todos
- ✅ Add, check, and delete checklist items
- 💾 Persistent storage using localStorage
- 🎨 Clean, modern, responsive design
- 🚀 No dependencies - just open and use

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

## Project Structure

```
to_do/
├── .github/
│   └── workflows/
│       └── deploy.yml       # GitHub Actions workflow for auto-deployment
├── .gitignore               # Git ignore file
├── index.html               # Main application file (HTML + CSS + JS)
└── README.md                # This file
```

## Local Development

To run locally, simply open `index.html` in your web browser:

```bash
open index.html
```

Or double-click the file in your file manager.

## Making Updates

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

## How It Works

- **Frontend Only**: No backend or database required
- **localStorage**: All data is saved in your browser's localStorage
- **Static Deployment**: Hosted on GitHub Pages as static files
- **Auto-Deploy**: Every push to `main` triggers automatic deployment

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

### GitHub Pages Not Deploying

1. Verify Pages is enabled with "GitHub Actions" as source
2. Check Actions tab for error messages
3. Ensure workflow has proper permissions in repository settings

### Local Changes Not Showing

If localStorage data seems stuck:
- Clear browser cache and localStorage
- Open browser DevTools > Application > Local Storage > Clear
