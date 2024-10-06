<!-- Project Title -->

# Setup Eslint and Prettier for React in VSCode

<!-- Table of Contents -->

## Table of Contents:

- [Editor Setup](#editor-setup)
  - [Plugins](#plugins)
  - [Settings](#settings)
  - [Set Line Breaks](#set-line-breaks)
- [Linting Setup](#linting-setup)
  - [Dependencies](#dependencies)
  - [Configure Eslint and Prettier](#configure-eslint-and-prettier)

<!-- Editor Setup -->

## Editor Setup

You can use any plugin as you wish to. Here, I'm using VSCode editor.

### Plugins

You need to install the following plugins:

- **ESLint** - Microsoft
- **Prettier - Code formatter** - Prettier
- Learn with Sumit (Peace of the eye - Dracula version) - Sumit Saha **(Optional)**

### Settings

Follow the steps to create `settings.json` file inside the project root:

1. Create a folder/directory named `.vscode` inside the project root.
2. Create a file named `settings.json` inside the `.vscode` folder/directory.
3. Copy and paste the below `json` object into the `settings.json` file and save it.

```sh
{
  // Theme
  "workbench.colorTheme": "Learn with Sumit - Peace of the eye - Dracula version",

  // config related to code formatting
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": "explicit",
    "source.fixAll.tslint": "explicit",
    "source.organizeImports": "explicit"
  },
  "eslint.run": "onSave",
  "emmet.includeLanguages": {
    "javascript": "javascriptreact"
  },
  "path-autocomplete.extensionOnImport": true,
  "path-autocomplete.excludedItems": {
    "*/.js": {
      "when": "**"
    },
    "*/.jsx": {
      "when": "**"
    }
  },
  "javascript.validate.enable": false,
  "typescript.validate.enable": false
}
```

If you follow all the previous steps correctly, your vscode should look like this.

## Set Line Breaks (If needed)

Make sure in your VS Code Editor, "LF" is selected as line feed instead of CRLF (Carriage return and line feed). To do that, just click LF/CRLF in bottom right corner of editor, click it and change it to "LF". If you don't do that, you may have face errors.

<img src="./assets/images/eslint-prettier-window.png" style="max-width: 100%; height: auto; object-fit: cover;" />

## Contact

Amin Babu - <a href="mailto:amin.babu.bd@gmail.com">amin.babu.bd@gmail.com</a>
