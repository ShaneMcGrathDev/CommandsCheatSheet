# Developer Command Cheat Sheet

## Table of Contents
- [Quick Commands Reference](#quick-commands-reference)
  - [NPM Commands](#npm-commands)
  - [PowerShell Commands](#powershell-commands)
  - [Next.js Commands](#nextjs-commands)
  - [Git Commands](#git-commands)
  - [VS Code Commands](#vs-code-commands)
- [Command Glossary](#command-glossary)
- [⚠️ Warnings & Cautions](#-warnings--cautions)
- [Advanced Storage & Configuration](#advanced-storage--configuration)

---

## Quick Commands Reference

### NPM Commands

```bash
# Package Management
npm init                    # Initialize new package.json
npm init -y                 # Initialize with defaults
npm install                 # Install all dependencies
npm install <package>       # Install specific package
npm install -g <package>    # Install globally
npm install --save-dev <package>  # Install as dev dependency
npm uninstall <package>     # Remove package
npm update                  # Update all packages
npm outdated               # Check for outdated packages

# Running Scripts
npm start                   # Run start script
npm test                    # Run test script
npm run <script>           # Run custom script
npm run-script <script>    # Alternative syntax

# Package Info
npm list                    # List installed packages
npm list -g --depth=0      # List global packages
npm view <package>         # View package details
npm search <term>          # Search for packages

# Publishing
npm publish                # Publish to registry
npm version patch/minor/major  # Bump version
npm pack                   # Create tarball

# Cache & Config
npm cache clean --force    # Clear npm cache
npm config list           # Show config
npm config set <key> <value>  # Set config value
```

### PowerShell Commands

```powershell
# Navigation
Get-Location (pwd)         # Current directory
Set-Location (cd)          # Change directory
Get-ChildItem (ls, dir)    # List items
Push-Location             # Save current location
Pop-Location              # Return to saved location

# File Management

# -Recurse let's you delete everything within a directory not just the directory itself
# -Force let's you override any special restrictions, .git contains hidden and read-only files that are protected

Remove-Item "C:\Users\shane\projects\test_build" -Recurse -Force 


New-Item                   # Create file/folder
Remove-Item (rm, del)      # Delete items
Copy-Item (cp)            # Copy items
Move-Item (mv)            # Move/rename items
Get-Content (cat, type)    # Read file content
Set-Content               # Write to file
Add-Content               # Append to file

# Process Management
Get-Process (ps)          # List processes
Stop-Process              # Kill process
Start-Process             # Start process

# System Info
Get-ComputerInfo          # System information
Get-Service               # List services
Get-EventLog              # View event logs

# Network
Test-Connection (ping)     # Test connectivity
Invoke-WebRequest (curl)   # HTTP requests
Test-NetConnection        # Advanced network test

# PowerShell Specific
Get-Command               # Find commands
Get-Help                  # Get command help
Get-Module                # List modules
Import-Module             # Import module
Export-Csv                # Export data to CSV
ConvertTo-Json            # Convert to JSON
```

### Next.js Commands

```bash
# Development
npx create-next-app@latest  # Create new app
npm run dev                 # Start dev server (localhost:3000)
npm run build              # Build for production
npm run start              # Start production server
npm run lint               # Run ESLint

# With App Directory (Next.js 13+)
npx create-next-app@latest --app  # Create with app directory
npm run dev --turbo        # Dev with Turbopack

# Build & Export
npm run build              # Build application
npm run export             # Export static HTML
npm run analyze            # Analyze bundle size

# Testing
npm run test               # Run tests
npm run test:watch         # Run tests in watch mode
npm run e2e                # Run E2E tests

# Database (with Prisma)
npx prisma init            # Initialize Prisma
npx prisma generate        # Generate client
npx prisma db push         # Push schema changes
npx prisma migrate dev     # Create migration
npx prisma studio          # Open Prisma Studio
```

### Git Commands

```bash
# Repository Setup
git init                   # Initialize repository
git clone <url>            # Clone repository
git remote add origin <url> # Add remote

# Basic Workflow
git status                 # Check status
git add .                  # Stage all changes
git add <file>             # Stage specific file
git commit -m "message"    # Commit changes
git push                   # Push to remote
git pull                   # Pull from remote
git fetch                  # Fetch without merge

# Branching
git branch                 # List branches
git branch <name>          # Create branch
git checkout <branch>      # Switch branch
git checkout -b <branch>   # Create & switch
git merge <branch>         # Merge branch
git branch -d <branch>     # Delete branch

# History & Differences
git log                    # View history
git log --oneline          # Condensed history
git diff                   # Show changes
git diff --staged          # Show staged changes
git show <commit>          # Show commit details

# Undoing Changes
git reset HEAD <file>      # Unstage file
git checkout -- <file>     # Discard changes
git reset --soft HEAD~1    # Undo last commit (keep changes)
git reset --hard HEAD~1    # Undo last commit (discard changes)
git revert <commit>        # Revert commit

# Stashing
git stash                  # Stash changes
git stash pop              # Apply & remove stash
git stash list             # List stashes
git stash apply            # Apply stash

# Advanced
git rebase <branch>        # Rebase branch
git cherry-pick <commit>   # Apply specific commit
git bisect                 # Binary search for bugs
git tag <name>             # Create tag
git submodule add <url>    # Add submodule
```

### VS Code Commands

```bash
# Command Palette (Ctrl+Shift+P / Cmd+Shift+P)
>Preferences: Open Settings       # Open settings
>Developer: Reload Window         # Reload VS Code
>View: Toggle Terminal           # Open/close terminal
>File: Save All                  # Save all files
>Git: Clone                      # Clone repository
>Terminal: Create New Terminal   # New terminal

# Keyboard Shortcuts (Windows/Linux | Mac)
Ctrl+Shift+P | Cmd+Shift+P      # Command palette
Ctrl+P | Cmd+P                  # Quick file open
Ctrl+Shift+F | Cmd+Shift+F      # Search in files
Ctrl+Shift+E | Cmd+Shift+E      # Explorer panel
Ctrl+` | Cmd+`                  # Toggle terminal
Ctrl+B | Cmd+B                  # Toggle sidebar
Ctrl+K Ctrl+S | Cmd+K Cmd+S     # Keyboard shortcuts
F5                              # Start debugging
Shift+F5                        # Stop debugging
F9                              # Toggle breakpoint
Ctrl+/ | Cmd+/                  # Toggle line comment
Alt+Shift+F | Option+Shift+F    # Format document
Ctrl+Space | Cmd+Space          # Trigger suggestions
F12                             # Go to definition
Alt+F12 | Option+F12            # Peek definition
Shift+F12                       # Find all references
F2                              # Rename symbol
Ctrl+D | Cmd+D                  # Add selection to next match
Ctrl+Shift+L | Cmd+Shift+L      # Select all occurrences
Alt+Click | Option+Click        # Multi-cursor
Alt+Up/Down | Option+Up/Down    # Move line up/down
Alt+Shift+Up/Down               # Copy line up/down
Ctrl+Enter | Cmd+Enter          # Insert line below
Ctrl+Shift+K | Cmd+Shift+K      # Delete line
Ctrl+] | Cmd+]                  # Indent line
Ctrl+[ | Cmd+[                  # Outdent line
Ctrl+K Ctrl+0 | Cmd+K Cmd+0     # Fold all code
Ctrl+K Ctrl+J | Cmd+K Cmd+J     # Unfold all code

# Terminal Commands
Ctrl+Shift+` | Cmd+Shift+`      # Create new terminal
Ctrl+Shift+5 | Cmd+Shift+5      # Split terminal
Ctrl+PageUp/Down                # Switch terminal tabs
exit                            # Close terminal

# Extension Management (CLI)
code --list-extensions          # List installed
code --install-extension <id>   # Install extension
code --uninstall-extension <id> # Remove extension

# Useful Extensions Commands
ext install esbenp.prettier-vscode     # Prettier
ext install dbaeumer.vscode-eslint     # ESLint
ext install eamodio.gitlens            # GitLens
ext install ms-vsliveshare.vsliveshare # Live Share
ext install ritwickdey.liveserver      # Live Server
ext install github.copilot             # GitHub Copilot
```

---

## Command Glossary

### NPM Commands Explained

- **npm init**: Creates a package.json file with project metadata and dependencies
- **npm install**: Downloads and installs all dependencies listed in package.json
- **npm install <package>**: Installs a specific package and adds it to dependencies
- **npm install --save-dev**: Installs package only for development (not production)
- **npm uninstall**: Removes a package from node_modules and package.json
- **npm update**: Updates packages to their latest versions within version constraints
- **npm outdated**: Shows which packages have newer versions available
- **npm run**: Executes scripts defined in package.json
- **npm publish**: Uploads your package to the npm registry for others to use
- **npm cache clean**: Clears npm's cache to resolve installation issues

### PowerShell Commands Explained

- **Get-Location**: Shows current working directory path
- **Set-Location**: Changes to a different directory
- **Get-ChildItem**: Lists files and folders in current/specified directory
- **New-Item**: Creates new files or folders
- **Remove-Item**: Deletes files or folders (use -Recurse for folders)
- **Get-Process**: Shows running processes with CPU and memory usage
- **Stop-Process**: Terminates a running process
- **Test-Connection**: Checks network connectivity to a host
- **Get-Help**: Displays help information for PowerShell commands
- **Import-Module**: Loads additional PowerShell functionality

### Next.js Commands Explained

- **create-next-app**: Scaffolds a new Next.js application with best practices
- **npm run dev**: Starts development server with hot reloading
- **npm run build**: Creates optimized production build
- **npm run start**: Runs the production build locally
- **npm run lint**: Checks code for style and potential errors
- **--turbo**: Uses Turbopack for faster development builds
- **prisma generate**: Creates TypeScript types from database schema
- **prisma migrate**: Manages database schema changes over time

### Git Commands Explained

- **git init**: Creates a new Git repository in current directory
- **git clone**: Downloads a complete copy of a remote repository
- **git add**: Stages changes for the next commit
- **git commit**: Saves staged changes with a descriptive message
- **git push**: Uploads local commits to remote repository
- **git pull**: Downloads and merges remote changes
- **git branch**: Manages parallel versions of your code
- **git merge**: Combines changes from different branches
- **git reset**: Undoes commits or unstages files
- **git stash**: Temporarily saves uncommitted changes
- **git rebase**: Rewrites commit history for cleaner timeline

### VS Code Commands Explained

- **Command Palette (Ctrl+Shift+P)**: Access all VS Code commands and features
- **Quick Open (Ctrl+P)**: Quickly open files by typing partial names
- **Multi-cursor editing**: Edit multiple locations simultaneously
- **Go to Definition (F12)**: Jump to where a function/variable is defined
- **Find All References (Shift+F12)**: Find all uses of a symbol
- **Rename Symbol (F2)**: Safely rename variables/functions across files
- **Format Document**: Auto-format code according to style rules
- **Code folding**: Collapse/expand code sections for better navigation
- **Integrated Terminal**: Run commands without leaving VS Code
- **Extension management**: Add functionality through community extensions

---

## ⚠️ Warnings & Cautions

### 🔴 HIGH RISK Commands

#### NPM
- **`npm install -g`** without sudo/admin can fail on system directories
- **`npm cache clean --force`** can cause issues if done during installations
- **`npm publish`** is permanent - packages cannot be deleted, only deprecated
- **`npm update`** can break your app if packages have breaking changes

#### PowerShell
- **`Remove-Item -Recurse -Force`** deletes without confirmation
- **`Stop-Process -Force`** can crash system processes
- **`Set-ExecutionPolicy Unrestricted`** opens security vulnerabilities
- **Running scripts from internet** without reviewing can compromise system

#### Git
- **`git push --force`** can overwrite others' work permanently
- **`git reset --hard`** permanently deletes uncommitted changes
- **`git clean -fd`** removes untracked files forever
- **`git rebase`** on shared branches can cause conflicts for team
- **`git filter-branch`** rewrites entire history (use filter-repo instead)

### 🟡 MODERATE RISK Commands

#### NPM
- **`npm audit fix --force`** may introduce breaking changes
- **`npm dedupe`** can cause unexpected behavior with peer deps
- **Installing from GitHub** directly may get unstable code

#### PowerShell
- **`Get-Content` on large files** can consume excessive memory
- **Piping to `Remove-Item`** can delete more than intended
- **`Invoke-WebRequest`** without validation can download malware

#### Git
- **`git commit --amend`** on pushed commits requires force push
- **`git cherry-pick`** can cause duplicate commits
- **`git merge` without reviewing** can introduce bugs
- **Working on `main/master`** directly bypasses code review

### 🟢 Best Practices

1. **Always commit before risky operations**
   ```bash
   git add . && git commit -m "backup before risky operation"
   ```

2. **Use npm ci instead of npm install in production**
   ```bash
   npm ci  # Installs from lock file, faster and more reliable
   ```

3. **Test PowerShell commands with -WhatIf**
   ```powershell
   Remove-Item *.txt -WhatIf  # Shows what would happen
   ```

4. **Create branches for experiments**
   ```bash
   git checkout -b experiment/risky-changes
   ```

5. **Use version ranges carefully in package.json**
   ```json
   "dependencies": {
     "package": "~1.2.3"  // Patch updates only
     "package": "^1.2.3"  // Minor updates allowed
     "package": "1.2.3"   // Exact version only
   }
   ```

---

## Storage Recommendations

### Primary: GitHub Repository ✨
1. Create a new repository: `developer-cheatsheet`
2. Set to private if contains work-specific commands
3. Clone to both work and personal computers
4. Use GitHub's search to quickly find commands

### Alternative Storage Options:
- **GitHub Gist**: For quick access via URL
- **OneDrive/Google Drive**: With desktop sync
- **VS Code Snippets**: For frequently used commands
- **Terminal aliases**: For most common operations

### Quick Setup:
```bash
# Create GitHub repo and push
git init
git add developer-cheatsheet.md
git commit -m "Initial cheatsheet"
git remote add origin https://github.com/yourusername/developer-cheatsheet.git
git push -u origin main
```

---

*Last updated: November 2024*

---

## Advanced Storage & Configuration

### GitHub Gist 📝

GitHub Gist is a simple way to share code snippets and notes. Unlike regular repositories, Gists are:
- **Lightweight**: Single or multiple files without full repo structure
- **Quick to create**: No need for repository setup
- **Shareable**: Each Gist gets a unique URL
- **Version controlled**: Full Git history for changes

**Creating a Gist:**
```bash
# Using GitHub CLI
gh gist create developer-cheatsheet.md --public

# Or via web:
# 1. Go to https://gist.github.com
# 2. Paste your content
# 3. Name it "developer-cheatsheet.md"
# 4. Create secret or public gist
```

**Accessing Your Gist:**
- Direct URL: `https://gist.github.com/yourusername/gist-id`
- Raw file: Add `/raw` to the URL
- Clone locally: `git clone https://gist.github.com/gist-id.git`

### Terminal Profile (Shell Configuration) 🖥️

Terminal profiles let you create custom command shortcuts (aliases) and functions that persist across sessions.

**Bash (.bashrc or .bash_profile):**
```bash
# Add to ~/.bashrc or ~/.bash_profile

# NPM Aliases
alias ni="npm install"
alias nid="npm install --save-dev"
alias nr="npm run"
alias nrd="npm run dev"
alias nrb="npm run build"

# Git Aliases
alias gs="git status"
alias ga="git add ."
alias gc="git commit -m"
alias gp="git push"
alias gpl="git pull"
alias gco="git checkout"
alias gb="git branch"

# Directory Navigation
alias ..="cd .."
alias ...="cd ../.."
alias dev="cd ~/Development"

# Custom Functions
mkcd() {
    mkdir -p "$1" && cd "$1"
}

# Show git branch in prompt
parse_git_branch() {
    git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}
PS1="\u@\h \W\$(parse_git_branch) $ "
```

**PowerShell Profile:**
```powershell
# Add to $PROFILE (usually ~/Documents/PowerShell/Microsoft.PowerShell_profile.ps1)

# NPM Aliases
Set-Alias ni npm install
function nid { npm install --save-dev $args }
function nr { npm run $args }

# Git Aliases
function gs { git status }
function ga { git add . }
function gc { param($m) git commit -m $m }
function gp { git push }

# Navigation
function .. { Set-Location .. }
function dev { Set-Location ~/Development }

# Custom prompt with git branch
function prompt {
    $branch = git branch --show-current 2>$null
    if ($branch) {
        Write-Host "$PWD" -NoNewline -ForegroundColor Green
        Write-Host " ($branch)" -NoNewline -ForegroundColor Yellow
        Write-Host " >" -NoNewline
    } else {
        Write-Host "$PWD >" -NoNewline
    }
    return " "
}
```

**Applying Changes:**
```bash
# Bash
source ~/.bashrc

# PowerShell
. $PROFILE
```

### VS Code Snippets 🚀

VS Code snippets are templates that expand into code blocks, saving typing time.

**Creating Custom Snippets:**

1. **Open User Snippets:**
   - Ctrl+Shift+P → "Preferences: Configure User Snippets"
   - Choose language (e.g., javascript.json)

2. **Snippet Structure:**
```json
{
    "Console Log": {
        "prefix": "clg",
        "body": [
            "console.log('$1');",
            "$2"
        ],
        "description": "Console log statement"
    },
    
    "React Functional Component": {
        "prefix": "rfc",
        "body": [
            "import React from 'react';",
            "",
            "const ${1:ComponentName} = () => {",
            "    return (",
            "        <div>",
            "            $2",
            "        </div>",
            "    );",
            "};",
            "",
            "export default ${1:ComponentName};"
        ],
        "description": "React functional component"
    },
    
    "Try Catch Block": {
        "prefix": "tryc",
        "body": [
            "try {",
            "    $1",
            "} catch (error) {",
            "    console.error('Error:', error);",
            "    $2",
            "}"
        ],
        "description": "Try catch block"
    },
    
    "Async Function": {
        "prefix": "afn",
        "body": [
            "const ${1:functionName} = async () => {",
            "    try {",
            "        $2",
            "    } catch (error) {",
            "        console.error('Error:', error);",
            "    }",
            "};"
        ],
        "description": "Async arrow function"
    }
}
```

**Using Snippets:**
1. Type the prefix (e.g., `clg`)
2. Press Tab to expand
3. Use Tab to jump between placeholders ($1, $2, etc.)

**Project-Specific Snippets:**
Create `.vscode/project.code-snippets` in your project root for team-shared snippets.

### Combining All Storage Methods 🎯

**Recommended Setup:**
1. **GitHub Repo**: Full cheat sheet and documentation
2. **Gist**: Quick reference cards for specific topics
3. **Terminal Profile**: Aliases for most-used commands
4. **VS Code Snippets**: Code templates and boilerplate

**Sync Across Devices:**
```bash
# Clone your dotfiles repo
git clone https://github.com/yourusername/dotfiles.git
cd dotfiles

# Link config files
ln -s ~/dotfiles/.bashrc ~/.bashrc
ln -s ~/dotfiles/.gitconfig ~/.gitconfig

# VS Code Settings Sync
# Use built-in Settings Sync (Sign in with GitHub/Microsoft)
```

**Quick Access Script:**
```bash
#!/bin/bash
# Save as 'cheat' and make executable

case "$1" in
    npm) curl https://gist.github.com/.../npm-commands.md ;;
    git) curl https://gist.github.com/.../git-commands.md ;;
    *) echo "Usage: cheat [npm|git|ps|next]" ;;
esac
```

---

*Last updated: November 2024*