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
  "[javascript]": {
    "editor.formatOnSave": false,
    "editor.defaultFormatter": null
  },
  "[javascriptreact]": {
    "editor.formatOnSave": false,
    "editor.defaultFormatter": null
  },
  "javascript.validate.enable": false, //disable all built-in syntax checking
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true,
    "source.fixAll.tslint": true,
    "source.organizeImports": true
  },
  "eslint.alwaysShowStatus": true,
  // emmet
  "emmet.triggerExpansionOnTab": true,
  "emmet.includeLanguages": {
    "javascript": "javascriptreact"
  }
}

```

If you follow all the previous steps correctly, your vscode should look like this.

## Set Line Breaks

Make sure in your VS Code Editor, "LF" is selected as line feed instead of CRLF (Carriage return and line feed). To do that, just click LF/CRLF in bottom right corner of editor, click it and change it to "LF". If you don't do that, you may have face errors.

<img src="./assets/images/eslint-prettier-window.png" style="max-width: 100%; height: auto; object-fit: cover;" />

## Linting Setup

In order to lint and format React project automatically according to most popular airbnb style guide, it is recommended to follow the instructions below:

### Dependencies

Install the following dev dependencies one by one.

```sh
npm i -D @babel/core @babel/eslint-parser prettier eslint-config-prettier eslint-plugin-prettier @babel/preset-react
```

Or, if you are using `yarn` as your default package manager, try this:

```sh
yarn add -D @babel/core @babel/eslint-parser prettier eslint-config-prettier eslint-plugin-prettier @babel/preset-react
```

To follow airbnb style guide run the command:

```sh
npx install-peerdeps --dev eslint-config-airbnb
```

### Configure ESLint and Prettier

Now its time to configure the ESLint and Prettier plugins to work together poperly. Create a linting config file manually in the project root folder/directory named `.eslintrc.json`

Copy and paste the followings into the `.eslintrc.json` file.

```sh
{
  "extends": [
    "airbnb",
    "airbnb/hooks",
    "eslint:recommended",
    "prettier",
    "plugin:jsx-a11y/recommended",
    "plugin:react/jsx-runtime"
  ],
  "parser": "@babel/eslint-parser",
  "parserOptions": {
    "requireConfigFile": false,
    "babelOptions": {
      "babelrc": false,
      "configFile": false,
      "presets": ["@babel/preset-react"]
    }
  },
  "env": {
    "browser": true,
    "node": true,
    "es2022": true,
    "jest": true
  },
  "rules": {
    "react-hooks/rules-of-hooks": "error",
    "no-console": 0,
    "react/state-in-constructor": 0,
    "indent": 0,
    "linebreak-style": 0,
    "react/prop-types": 0,
    "jsx-a11y/click-events-have-key-events": 0,
    "react/jsx-filename-extension": [
      1,
      {
        "extensions": [".js", ".jsx"]
      }
    ],
    "prettier/prettier": [
      "error",
      {
        "trailingComma": "es5",
        "singleQuote": true,
        "printWidth": 100,
        "tabWidth": 4,
        "semi": true,
        "endOfLine": "auto"
      }
    ]
  },
  "plugins": ["prettier", "react", "react-hooks"]
}
```

## Contact

Amin Babu - <a href="mailto:amin.babu.bd@gmail.com">amin.babu.bd@gmail.com</a>
