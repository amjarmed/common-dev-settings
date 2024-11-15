# common files and setting for web development to use in any new project with vscode

### **1. Project-specific Settings**

Store settings that apply only to the current project. These settings override global settings when you open the project.

- File: `.vscode/settings.json`
- Example: Configure formatting, tab size, or language-specific behaviors.
  ```json
  {
    "editor.tabSize": 2,
    "editor.formatOnSave": true,
    "files.exclude": {
      "**/.git": true,
      "**/node_modules": true
    },
    "typescript.tsdk": "./node_modules/typescript/lib"
  }
  ```

---

### **2. Task Automation**

Define custom tasks for build processes, testing, or running scripts.

- File: `.vscode/tasks.json`
- Example: Run a Node.js server or a build process.
  ```json
  {
    "version": "2.0.0",
    "tasks": [
      {
        "label": "Run Server",
        "type": "shell",
        "command": "npm start",
        "problemMatcher": []
      },
      {
        "label": "Build",
        "type": "shell",
        "command": "npm run build",
        "problemMatcher": []
      }
    ]
  }
  ```

---

### **3. Debugging Configurations**

Set up debugging configurations for different environments (e.g., Node.js, Python, or browser debugging).

- File: `.vscode/launch.json`
- Example: Debug a Node.js application.
  ```json
  {
    "version": "0.2.0",
    "configurations": [
      {
        "type": "node",
        "request": "launch",
        "name": "Launch Program",
        "program": "${workspaceFolder}/src/app.js"
      }
    ]
  }
  ```

---

### **4. Extensions Recommendations**

Recommend extensions for the project. When a teammate opens the project, VSCode will suggest installing these extensions.

- File: `.vscode/extensions.json`
- Example: Recommend extensions like ESLint and Prettier.
  ```json
  {
    "recommendations": [
      "dbaeumer.vscode-eslint",
      "esbenp.prettier-vscode",
      "ms-vscode.vscode-typescript-tslint-plugin"
    ]
  }
  ```

---

### **5. Snippets**

Define custom code snippets for the project, making repetitive coding tasks faster.

- File: `.vscode/<language>.code-snippets` (e.g., `javascript.code-snippets`)
- Example: Add a React component snippet.
  ```json
  {
    "React Functional Component": {
      "prefix": "rfc",
      "body": [
        "import React from 'react';",
        "",
        "const ${1:ComponentName} = () => {",
        "  return (",
        "    <div>",
        "      ${2:content}",
        "    </div>",
        "  );",
        "};",
        "",
        "export default ${1:ComponentName};"
      ],
      "description": "Create a React Functional Component"
    }
  }
  ```

---

### **6. Git Hooks or Workflow Configurations**

Configure Git hooks or tools to improve collaboration.

- File: `.vscode/settings.json` (Git-related settings)
- Example: Enable Git integration for specific files.
  ```json
  {
    "git.ignoreLimitWarning": true,
    "git.enableSmartCommit": true
  }
  ```

---

### **7. Code Linting and Formatting**

Set project-specific linting and formatting rules, often paired with extensions like ESLint and Prettier.

- File: `.vscode/settings.json`
- Example:
  ```json
  {
    "eslint.enable": true,
    "eslint.options": {
      "configFile": ".eslintrc.json"
    },
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  }
  ```

---

### **8. Custom Keybindings**

Define keybindings specific to the project for a consistent team workflow.

- File: `.vscode/keybindings.json`
- Example:
  ```json
  [
    {
      "key": "ctrl+shift+b",
      "command": "workbench.action.tasks.runTask",
      "args": "Build"
    }
  ]
  ```

---

### **9. Configure Language Settings**

Override default settings for specific languages in the project.

- File: `.vscode/settings.json`
- Example: Use different formatting for JSON files.
  ```json
  {
    "[json]": {
      "editor.tabSize": 4
    }
  }
  ```

---

### **10. Workspace-Specific Plugins or Tools**

Configure tools like Jest, Mocha, or Cypress for testing and ensure the correct environment is used for them.

- Example for Jest (`launch.json`):
  ```json
  {
    "version": "0.2.0",
    "configurations": [
      {
        "type": "node",
        "request": "launch",
        "name": "Jest Tests",
        "program": "${workspaceFolder}/node_modules/jest/bin/jest.js",
        "args": ["--runInBand"],
        "console": "integratedTerminal",
        "internalConsoleOptions": "neverOpen"
      }
    ]
  }
  ```

---

### Commonly Used Files in `.vscode`

| File Name                  | Purpose                                         |
| -------------------------- | ----------------------------------------------- |
| `settings.json`            | Project-specific editor and workspace settings. |
| `tasks.json`               | Define custom automation tasks.                 |
| `launch.json`              | Configure debugging settings.                   |
| `extensions.json`          | Recommend extensions for collaborators.         |
| `<language>.code-snippets` | Define language-specific snippets.              |

---

## other setting

```bash

git config --global fetch.autosync true
git config --global pull.rebase false

```
