# Style Guide

Setting up style guides in VSCode using Prettier, AirBnB, ESLint, Husky and Lint Staged.

## JavaScript

```sh
yarn add --dev eslint prettier eslint-config-airbnb-base eslint-plugin-import eslint-config-prettier eslint-plugin-prettier lint-staged husky
```

Create `.eslintrc.json`.

```sh
touch .eslintrc.json
```

Add this ESLint setting.

```json
{
  "extends": ["airbnb-base", "prettier"],
  "plugins": ["prettier"],
  "rules": {
    "prettier/prettier": ["error"]
  }
}
```

Create `.prettierrc`.

```sh
touch .prettierrc
```

```json
{
  "trailingComma": "es5",
  "printWidth": 100,
  "singleQuote": true
}
```

Add `"editor.formatOnSave": true` into user setting in VSCode.

Add precommit scripts into `package.json`.

```json
"husky": {
  "hooks": {
    "pre-commit": "lint-staged"
  }
},
"lint-staged": {
  "*.{js,css,md}": [
    "eslint",
    "git add"
  ]
},
```

## React

```sh
yarn add --dev eslint eslint-config-airbnb eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react prettier eslint-config-prettier eslint-plugin-prettier lint-staged husky
```

Create `.eslintrc.json`.

```sh
touch .eslintrc.json
```

Add this ESLint setting.

```json
{
  "extends": ["airbnb", "prettier", "prettier/react"],
  "rules": {
    "react/jsx-filename-extension": [
      1,
      {
        "extensions": [".js", ".jsx"]
      }
    ],
    "prettier/prettier": ["error"]
  },
  "plugins": ["prettier"]
}
```

Create `.prettierrc`.

```sh
touch .prettierrc
```

```json
{
  "trailingComma": "es5",
  "printWidth": 100,
  "singleQuote": true
}
```

Add `"editor.formatOnSave": true` into user setting in VSCode.

Add precommit scripts into `package.json`.

```json
"husky": {
  "hooks": {
    "pre-commit": "lint-staged"
  }
},
"lint-staged": {
  "*.{js,css}": [
    "eslint",
    "git add"
  ]
},
```

## References

- [How to set up ES Lint for Airbnb, Vue JS, and VS Code](https://medium.com/@agm1984/how-to-set-up-es-lint-for-airbnb-vue-js-and-vs-code-a5ef5ac671e8)
- [Integrating Prettier + ESLint + Airbnb Style Guide in VSCode](https://blog.echobind.com/integrating-prettier-eslint-airbnb-style-guide-in-vscode-47f07b5d7d6a).
- [Setup ESLint and Prettier together for react and react-native projects in Visual Studio Code](https://medium.com/appstud/setup-eslint-and-prettier-together-for-react-and-react-native-projects-in-visual-studio-code-78772d58358d)
- [React/React-Native configure eslint (Airbnb), prettier and precommit with husky in one go for code quality](https://medium.com/innow8/react-react-native-configure-eslint-airbnb-prettier-and-precommit-with-husky-in-one-go-for-code-e89363e5f17f)
