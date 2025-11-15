# VS Code Full-Stack Developer Guide
## Next.js • TypeScript • React • Redux • Python Flask

---

## Table of Contents
- [Project Manager Setup](#project-manager-setup)
- [Essential Extensions](#essential-extensions)
- [Language-Specific Extensions](#language-specific-extensions)
- [VS Code Settings](#vs-code-settings)
- [Keyboard Shortcuts](#keyboard-shortcuts)
- [Debugging Configuration](#debugging-configuration)
- [Code Snippets](#code-snippets)
- [Productivity Tips](#productivity-tips)
- [Multi-Project Workflow](#multi-project-workflow)

---

## Project Manager Setup

### Installation & Basic Setup
```bash
# Install via VS Code
ext install alefragnani.project-manager
```

### Configuration
Add to your `settings.json` (`Ctrl+Shift+P` → "Open Settings JSON"):

```json
{
    // Project Manager Settings
    "projectManager.git.baseFolders": [
        "C:\\Users\\shane\\projects",
        "C:\\Users\\shane\\work",
        "C:\\Users\\shane\\personal"
    ],
    "projectManager.git.maxDepthRecursion": 2,
    "projectManager.git.ignoredFolders": [
        "node_modules", 
        "out", 
        "dist", 
        ".next",
        "__pycache__",
        "venv",
        ".venv"
    ],
    "projectManager.sortList": "Name",
    "projectManager.groupList": true,
    "projectManager.showParentFolderInfoOnDuplicates": true,
    "projectManager.cacheProjectsBetweenSessions": true,
    "projectManager.ignoreProjectsWithinProjects": true
}
```

### Project Manager Usage

**Saving Projects:**
1. Open project in VS Code
2. `Ctrl+Shift+P` → "Project Manager: Save Project"
3. Enter a name (can include tags like `[Frontend]` or `[API]`)

**Quick Access:**
- `Ctrl+Alt+P` - Quick switch between projects
- `Shift+Alt+P` - Open project in new window

**Organizing Projects:**
```json
// Group projects by type
"projectManager.tags": [
    "Frontend",
    "Backend",
    "Full-Stack",
    "Personal",
    "Work",
    "Next.js",
    "Flask"
]
```

---

## Essential Extensions

### Core Developer Pack
```bash
# Must-have extensions for all developers
ext install editorconfig.editorconfig          # EditorConfig
ext install eamodio.gitlens                    # GitLens
ext install usernamehw.errorlens               # Error Lens
ext install streetsidesoftware.code-spell-checker  # Spell Checker
ext install wayou.vscode-todo-highlight        # TODO Highlight
ext install gruntfuggly.todo-tree              # Todo Tree
ext install pnp.polacode                       # Code Screenshots
ext install wix.vscode-import-cost             # Import Cost
ext install formulahendry.auto-rename-tag      # Auto Rename Tag
ext install vincaslt.highlight-matching-tag    # Highlight Matching Tag
```

### Formatting & Linting
```bash
ext install esbenp.prettier-vscode             # Prettier
ext install dbaeumer.vscode-eslint             # ESLint
ext install stylelint.vscode-stylelint         # Stylelint
ext install foxundermoon.shell-format          # Shell formatting
```

### AI & Productivity
```bash
ext install github.copilot                     # GitHub Copilot
ext install github.copilot-chat                # Copilot Chat
ext install visualstudioexptteam.vscodeintellicode  # IntelliCode
ext install tabnine.tabnine-vscode             # Tabnine (alternative)
```

---

## Language-Specific Extensions

### TypeScript & JavaScript
```bash
ext install ms-vscode.vscode-typescript-next   # TS Nightly
ext install pmndrs.tsx-tools                   # TSX Tools
ext install unifiedjs.vscode-mdx               # MDX Support
ext install bradlc.vscode-tailwindcss          # Tailwind IntelliSense
ext install prisma.prisma                      # Prisma
ext install graphql.vscode-graphql             # GraphQL
ext install apollographql.vscode-apollo        # Apollo GraphQL
```

### React & Next.js
```bash
ext install dsznajder.es7-react-js-snippets    # ES7+ React snippets
ext install rodrigovallades.es7-react-js-snippets  # React snippets
ext install jpoissonnier.vscode-styled-components  # Styled Components
ext install styled-components.vscode-styled-components  # Official SC
ext install mhutchie.git-graph                 # Git Graph
ext install pflannery.vscode-versionlens       # Version Lens
```

### Redux
```bash
ext install jingkaizhao.vscode-redux-devtools  # Redux DevTools
ext install loyieking.redux-snippet-generator  # Redux Snippets
ext install dericcain.vscode-redux-starter     # Redux Starter
```

### Python & Flask
```bash
ext install ms-python.python                   # Python
ext install ms-python.vscode-pylance           # Pylance
ext install ms-python.black-formatter          # Black Formatter
ext install ms-python.isort                    # Import sorting
ext install ms-python.flake8                   # Flake8 linting
ext install njpwerner.autodocstring            # Docstring generator
ext install wholroyd.jinja                     # Jinja2 templates
ext install samuelcolvin.jinjahtml             # Jinja HTML
ext install kevinrose.vsc-python-indent        # Python indent
ext install littlefoxteam.vscode-python-test-adapter  # Test explorer
```

### Database & API
```bash
ext install mtxr.sqltools                      # SQL Tools
ext install mtxr.sqltools-driver-sqlite        # SQLite
ext install mtxr.sqltools-driver-pg            # PostgreSQL
ext install mongodb.mongodb-vscode             # MongoDB
ext install rangav.vscode-thunder-client       # Thunder Client (Postman alternative)
ext install humao.rest-client                  # REST Client
```

---

## VS Code Settings

### Optimized settings.json for Full-Stack Development

```json
{
    // Editor Settings
    "editor.fontSize": 14,
    "editor.fontFamily": "'Fira Code', 'Cascadia Code', Consolas, monospace",
    "editor.fontLigatures": true,
    "editor.tabSize": 2,
    "editor.detectIndentation": true,
    "editor.renderWhitespace": "selection",
    "editor.rulers": [80, 100],
    "editor.bracketPairColorization.enabled": true,
    "editor.guides.bracketPairs": "active",
    "editor.stickyScroll.enabled": true,
    "editor.minimap.enabled": false,
    "editor.linkedEditing": true,
    "editor.snippetSuggestions": "top",
    "editor.suggest.insertMode": "replace",
    "editor.accessibilitySupport": "off",
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true,
        "source.organizeImports": true
    },

    // Terminal Settings
    "terminal.integrated.fontSize": 14,
    "terminal.integrated.defaultProfile.windows": "PowerShell",
    "terminal.integrated.env.windows": {
        "NODE_ENV": "development"
    },

    // File Settings
    "files.autoSave": "onFocusChange",
    "files.trimTrailingWhitespace": true,
    "files.insertFinalNewline": true,
    "files.associations": {
        "*.js": "javascriptreact",
        "*.tsx": "typescriptreact",
        "*.env.*": "dotenv"
    },
    "files.exclude": {
        "**/.git": true,
        "**/.DS_Store": true,
        "**/node_modules": true,
        "**/.next": true,
        "**/__pycache__": true,
        "**/*.pyc": true,
        "**/venv": true
    },

    // Search Settings
    "search.exclude": {
        "**/node_modules": true,
        "**/bower_components": true,
        "**/*.code-search": true,
        "**/.next": true,
        "**/build": true,
        "**/dist": true
    },

    // TypeScript/JavaScript Settings
    "typescript.updateImportsOnFileMove.enabled": "always",
    "typescript.preferences.importModuleSpecifier": "relative",
    "javascript.updateImportsOnFileMove.enabled": "always",
    "typescript.tsserver.log": "off",
    "[typescript]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "[typescriptreact]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "[javascript]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "[javascriptreact]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },

    // Python Settings
    "[python]": {
        "editor.defaultFormatter": "ms-python.black-formatter",
        "editor.tabSize": 4,
        "editor.insertSpaces": true,
        "editor.codeActionsOnSave": {
            "source.organizeImports": true
        }
    },
    "python.linting.enabled": true,
    "python.linting.flake8Enabled": true,
    "python.formatting.provider": "black",
    "python.testing.pytestEnabled": true,
    "python.terminal.activateEnvironment": true,
    "python.defaultInterpreterPath": "python",

    // Emmet for React
    "emmet.includeLanguages": {
        "javascript": "javascriptreact",
        "typescript": "typescriptreact"
    },
    "emmet.triggerExpansionOnTab": true,

    // Prettier Settings
    "prettier.semi": true,
    "prettier.singleQuote": true,
    "prettier.tabWidth": 2,
    "prettier.useTabs": false,
    "prettier.printWidth": 100,
    "prettier.trailingComma": "es5",
    "prettier.arrowParens": "always",

    // ESLint Settings
    "eslint.validate": [
        "javascript",
        "javascriptreact",
        "typescript",
        "typescriptreact"
    ],
    "eslint.format.enable": false,
    "eslint.packageManager": "npm",

    // Git Settings
    "git.autofetch": true,
    "git.confirmSync": false,
    "git.enableSmartCommit": true,
    "gitlens.hovers.currentLine.over": "line",
    "gitlens.codeLens.enabled": false,

    // Error Lens Settings
    "errorLens.enabled": true,
    "errorLens.delay": 500,
    "errorLens.errorBackground": "rgba(240,0,0,0.1)",
    "errorLens.warningBackground": "rgba(255,200,0,0.1)",

    // Copilot Settings
    "github.copilot.enable": {
        "*": true,
        "yaml": true,
        "plaintext": false,
        "markdown": true
    }
}
```

---

## Keyboard Shortcuts

### Custom Keybindings for Full-Stack Development
Add to `keybindings.json` (`Ctrl+K Ctrl+S` → Click the `{}` icon):

```json
[
    // Quick file switching
    {
        "key": "alt+1",
        "command": "workbench.action.openEditorAtIndex1"
    },
    {
        "key": "alt+2",
        "command": "workbench.action.openEditorAtIndex2"
    },
    
    // Terminal shortcuts
    {
        "key": "ctrl+alt+n",
        "command": "workbench.action.terminal.new"
    },
    {
        "key": "ctrl+alt+t",
        "command": "workbench.action.terminal.focus"
    },
    
    // Quick actions
    {
        "key": "ctrl+alt+f",
        "command": "editor.action.formatDocument"
    },
    {
        "key": "ctrl+alt+o",
        "command": "editor.action.organizeImports"
    },
    
    // Git shortcuts
    {
        "key": "ctrl+shift+g s",
        "command": "git.status"
    },
    {
        "key": "ctrl+shift+g p",
        "command": "git.push"
    },
    
    // Project Manager
    {
        "key": "ctrl+alt+p",
        "command": "projectManager.listProjects"
    },
    {
        "key": "shift+alt+p",
        "command": "projectManager.listProjectsNewWindow"
    },
    
    // Testing
    {
        "key": "ctrl+shift+t",
        "command": "testing.runAll"
    },
    {
        "key": "ctrl+alt+d",
        "command": "testing.debugAll"
    }
]
```

---

## Debugging Configuration

### Next.js Debugging
Create `.vscode/launch.json`:

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Next.js: debug server-side",
            "type": "node-terminal",
            "request": "launch",
            "command": "npm run dev"
        },
        {
            "name": "Next.js: debug client-side",
            "type": "chrome",
            "request": "launch",
            "url": "http://localhost:3000",
            "webRoot": "${workspaceFolder}"
        },
        {
            "name": "Next.js: debug full stack",
            "type": "node-terminal",
            "request": "launch",
            "command": "npm run dev",
            "serverReadyAction": {
                "action": "debugWithChrome",
                "pattern": "ready - started server on .+, url: (https?://.+)",
                "uriFormat": "%s",
                "webRoot": "${workspaceFolder}"
            }
        }
    ]
}
```

### Python Flask Debugging
Add to `.vscode/launch.json`:

```json
{
    "configurations": [
        {
            "name": "Python: Flask",
            "type": "python",
            "request": "launch",
            "module": "flask",
            "env": {
                "FLASK_APP": "app.py",
                "FLASK_ENV": "development",
                "FLASK_DEBUG": "1"
            },
            "args": [
                "run",
                "--no-debugger",
                "--no-reload",
                "--port",
                "5000"
            ],
            "jinja": true,
            "justMyCode": true
        },
        {
            "name": "Python: Current File",
            "type": "python",
            "request": "launch",
            "program": "${file}",
            "console": "integratedTerminal",
            "justMyCode": true
        }
    ]
}
```

### Full-Stack Debugging (Frontend + Backend)
```json
{
    "compounds": [
        {
            "name": "Full Stack",
            "configurations": [
                "Next.js: debug server-side",
                "Python: Flask"
            ],
            "stopAll": true
        }
    ]
}
```

---

## Code Snippets

### React/TypeScript Snippets
Create/update `.vscode/typescriptreact.code-snippets`:

```json
{
    "Next.js Page Component": {
        "prefix": "nextpage",
        "body": [
            "import { GetServerSideProps, NextPage } from 'next';",
            "import Head from 'next/head';",
            "",
            "interface ${1:PageName}Props {",
            "  $2",
            "}",
            "",
            "const ${1:PageName}: NextPage<${1:PageName}Props> = ({ $3 }) => {",
            "  return (",
            "    <>",
            "      <Head>",
            "        <title>${4:Page Title}</title>",
            "        <meta name=\"description\" content=\"${5:Page description}\" />",
            "      </Head>",
            "      <main>",
            "        $0",
            "      </main>",
            "    </>",
            "  );",
            "};",
            "",
            "export const getServerSideProps: GetServerSideProps = async (context) => {",
            "  return {",
            "    props: {},",
            "  };",
            "};",
            "",
            "export default ${1:PageName};"
        ]
    },
    
    "React FC with Redux": {
        "prefix": "rfcredux",
        "body": [
            "import React from 'react';",
            "import { useSelector, useDispatch } from 'react-redux';",
            "import { RootState } from '@/store';",
            "",
            "interface ${1:ComponentName}Props {",
            "  $2",
            "}",
            "",
            "export const ${1:ComponentName}: React.FC<${1:ComponentName}Props> = ({ $3 }) => {",
            "  const dispatch = useDispatch();",
            "  const { $4 } = useSelector((state: RootState) => state.$5);",
            "",
            "  return (",
            "    <div>",
            "      $0",
            "    </div>",
            "  );",
            "};"
        ]
    },
    
    "Custom Hook": {
        "prefix": "customhook",
        "body": [
            "import { useState, useEffect } from 'react';",
            "",
            "export const use${1:HookName} = (${2:params}) => {",
            "  const [${3:state}, set${3/(.*)/${1:/capitalize}/}] = useState(${4:initialValue});",
            "",
            "  useEffect(() => {",
            "    $0",
            "  }, [${5:dependencies}]);",
            "",
            "  return { ${3:state} };",
            "};"
        ]
    },
    
    "Redux Slice": {
        "prefix": "reduxslice",
        "body": [
            "import { createSlice, PayloadAction } from '@reduxjs/toolkit';",
            "",
            "interface ${1:SliceName}State {",
            "  ${2:value}: ${3:type};",
            "}",
            "",
            "const initialState: ${1:SliceName}State = {",
            "  ${2:value}: ${4:initialValue},",
            "};",
            "",
            "const ${5:${1/(.*)/${1:/downcase}/}}Slice = createSlice({",
            "  name: '${5:${1/(.*)/${1:/downcase}/}}',",
            "  initialState,",
            "  reducers: {",
            "    ${6:actionName}: (state, action: PayloadAction<${7:PayloadType}>) => {",
            "      $0",
            "    },",
            "  },",
            "});",
            "",
            "export const { ${6:actionName} } = ${5:${1/(.*)/${1:/downcase}/}}Slice.actions;",
            "export default ${5:${1/(.*)/${1:/downcase}/}}Slice.reducer;"
        ]
    }
}
```

### Python Flask Snippets
Create `.vscode/python.code-snippets`:

```json
{
    "Flask Route": {
        "prefix": "froute",
        "body": [
            "@app.route('/${1:endpoint}', methods=['${2|GET,POST,PUT,DELETE|}'])",
            "def ${3:function_name}():",
            "    \"\"\"${4:Route description}\"\"\"",
            "    try:",
            "        $0",
            "        return jsonify({'success': True}), 200",
            "    except Exception as e:",
            "        return jsonify({'error': str(e)}), 500"
        ]
    },
    
    "Flask Blueprint": {
        "prefix": "fblueprint",
        "body": [
            "from flask import Blueprint, jsonify, request",
            "",
            "${1:blueprint_name}_bp = Blueprint('${1:blueprint_name}', __name__, url_prefix='/${2:api/v1}/${1:blueprint_name}')",
            "",
            "@${1:blueprint_name}_bp.route('/', methods=['GET'])",
            "def get_${1:blueprint_name}():",
            "    \"\"\"Get all ${1:blueprint_name}\"\"\"",
            "    $0",
            "    return jsonify({'data': []}), 200"
        ]
    },
    
    "Flask Model": {
        "prefix": "fmodel",
        "body": [
            "from datetime import datetime",
            "from app import db",
            "",
            "class ${1:ModelName}(db.Model):",
            "    __tablename__ = '${2:${1/([A-Z])/_${1:/downcase}/g}}'",
            "    ",
            "    id = db.Column(db.Integer, primary_key=True)",
            "    ${3:field_name} = db.Column(db.${4|String(255),Integer,Boolean,DateTime,Float|}, nullable=${5|False,True|})",
            "    created_at = db.Column(db.DateTime, default=datetime.utcnow)",
            "    updated_at = db.Column(db.DateTime, default=datetime.utcnow, onupdate=datetime.utcnow)",
            "    ",
            "    def __repr__(self):",
            "        return f'<${1:ModelName} {self.id}>'"
        ]
    }
}
```

---

## Productivity Tips

### 1. **Multi-Cursor Editing**
- `Alt + Click` - Add cursor
- `Ctrl + Alt + Up/Down` - Add cursor above/below
- `Ctrl + D` - Select next occurrence
- `Ctrl + Shift + L` - Select all occurrences

### 2. **Quick Navigation**
- `Ctrl + P` - Quick file open
- `Ctrl + G` - Go to line
- `Ctrl + R` - Go to symbol in workspace
- `Ctrl + Shift + O` - Go to symbol in file
- `F12` - Go to definition
- `Alt + F12` - Peek definition

### 3. **Refactoring Shortcuts**
- `F2` - Rename symbol
- `Ctrl + .` - Quick fix
- `Shift + Alt + O` - Organize imports
- `Ctrl + Shift + R` - Refactor menu

### 4. **Terminal Tips**
- Split terminal: `Ctrl + Shift + 5`
- Kill terminal: `Ctrl + Shift + X`
- Create new terminal: `` Ctrl + Shift + ` ``
- Toggle terminal: `` Ctrl + ` ``

### 5. **Git Integration**
- `Ctrl + Shift + G` - Source control
- `Ctrl + Enter` - Commit
- Click on line numbers to see Git blame

### 6. **Live Share for Collaboration**
```bash
ext install ms-vsliveshare.vsliveshare
```
- Share debugging sessions
- Share terminals
- Share servers (localhost)

### 7. **Workspace-Specific Settings**
Create `.vscode/settings.json` in your project:
```json
{
    "editor.formatOnSave": true,
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
    },
    "python.defaultInterpreterPath": "./venv/bin/python"
}
```

### 8. **Task Automation**
Create `.vscode/tasks.json`:
```json
{
    "version": "2.0.0",
    "tasks": [
        {
            "label": "Start Dev Environment",
            "dependsOn": [
                "Start Next.js",
                "Start Flask API"
            ],
            "group": {
                "kind": "build",
                "isDefault": true
            }
        },
        {
            "label": "Start Next.js",
            "type": "npm",
            "script": "dev",
            "isBackground": true,
            "problemMatcher": []
        },
        {
            "label": "Start Flask API",
            "type": "shell",
            "command": "python",
            "args": ["app.py"],
            "options": {
                "cwd": "${workspaceFolder}/backend"
            },
            "isBackground": true
        }
    ]
}
```

---

## Multi-Project Workflow

### Workspace Setup for Full-Stack Projects

Create `fullstack-workspace.code-workspace`:
```json
{
    "folders": [
        {
            "name": "Frontend (Next.js)",
            "path": "./frontend"
        },
        {
            "name": "Backend (Flask)",
            "path": "./backend"
        },
        {
            "name": "Shared Types",
            "path": "./shared"
        }
    ],
    "settings": {
        "files.exclude": {
            "**/node_modules": true,
            "**/__pycache__": true,
            "**/.next": true
        },
        "search.exclude": {
            "**/node_modules": true,
            "**/venv": true,
            "**/.next": true,
            "**/build": true
        },
        "typescript.tsdk": "frontend/node_modules/typescript/lib",
        "eslint.workingDirectories": [
            "./frontend"
        ],
        "python.defaultInterpreterPath": "./backend/venv/bin/python"
    },
    "extensions": {
        "recommendations": [
            "dbaeumer.vscode-eslint",
            "esbenp.prettier-vscode",
            "ms-python.python",
            "dsznajder.es7-react-js-snippets",
            "bradlc.vscode-tailwindcss"
        ]
    },
    "launch": {
        "version": "0.2.0",
        "configurations": [],
        "compounds": [
            {
                "name": "Full Stack Development",
                "configurations": [
                    "Next.js Dev",
                    "Flask Dev"
                ]
            }
        ]
    }
}
```

### Quick Project Templates

**Create new Next.js project:**
```bash
# Terminal command
npx create-next-app@latest my-app --typescript --tailwind --app --src-dir --import-alias "@/*"

# Add common dependencies
cd my-app
npm install @reduxjs/toolkit react-redux axios @tanstack/react-query
npm install -D @types/node
```

**Create new Flask project:**
```bash
# Terminal commands
mkdir my-flask-api && cd my-flask-api
python -m venv venv
# Windows: venv\Scripts\activate
# Mac/Linux: source venv/bin/activate
pip install flask flask-cors flask-sqlalchemy python-dotenv
pip freeze > requirements.txt

# Create basic structure
mkdir app
touch app/__init__.py app/routes.py app/models.py run.py
```

### Syncing Settings Across Machines

1. **Settings Sync (Built-in):**
   - Sign in with GitHub/Microsoft account
   - Turn on Settings Sync
   - Choose what to sync (settings, keybindings, extensions, etc.)

2. **Dotfiles Repository:**
   ```bash
   # Create a dotfiles repo with VS Code settings
   mkdir ~/dotfiles/vscode
   cp ~/.config/Code/User/settings.json ~/dotfiles/vscode/
   cp ~/.config/Code/User/keybindings.json ~/dotfiles/vscode/
   code --list-extensions > ~/dotfiles/vscode/extensions.txt
   ```

3. **Restore on new machine:**
   ```bash
   # Install extensions from list
   cat ~/dotfiles/vscode/extensions.txt | xargs -L 1 code --install-extension
   ```

---

## Troubleshooting Common Issues

### TypeScript/ESLint not working
```bash
# Reload window
Ctrl+Shift+P → "Developer: Reload Window"

# Clear cache
rm -rf node_modules/.cache
npm install
```

### Python interpreter not found
```bash
# Select interpreter
Ctrl+Shift+P → "Python: Select Interpreter"
# Choose the venv/bin/python path
```

### Slow performance
```json
// Add to settings.json
{
    "files.watcherExclude": {
        "**/node_modules/**": true,
        "**/.next/**": true,
        "**/build/**": true,
        "**/dist/**": true
    },
    "typescript.tsserver.maxTsServerMemory": 4096,
    "typescript.disableAutomaticTypeAcquisition": true
}
```

---

## Additional Resources

- **VS Code Docs**: https://code.visualstudio.com/docs
- **Next.js VS Code Guide**: https://nextjs.org/docs/advanced-features/debugging
- **Python in VS Code**: https://code.visualstudio.com/docs/python/python-tutorial
- **Redux DevTools**: https://github.com/reduxjs/redux-devtools

---

*Last updated: November 2024*