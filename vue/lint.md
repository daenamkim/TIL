# Linter Settings for Vue

I compared Google Style and AirBnB [here](https://medium.com/@uistephen/style-guides-for-linting-ecmascript-2015-eslint-common-google-airbnb-6c25fd3dff0), [here](https://hackernoon.com/what-javascript-code-style-is-the-most-popular-5a3f5bec1f6f).

### Conclusions

- AirBnB styles will be better because it looks more popular, readable, strict and ES6 styles.
- Adding precommit hook to block not clean codes for the bright future.

### Linter setting

- [VSCode ESLint plugin](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [VSCode Vetur plugin](https://marketplace.visualstudio.com/items?itemName=octref.vetur)

- Node.js

```sh
$ yarn global add eslint
$ yarn add -D babel-eslint eslint eslint-config-airbnb-base eslint-plugin-import eslint-plugin-vue
```

```json
{
    "env": {
        "es6": true,
        "browser": true,
        "jquery": true
    },
    "parserOptions": {
        "parser": "babel-eslint"
    },
    "extends": [
        "airbnb-base",
        "plugin:vue/recommended"
    ]
}

```

### Precommit hook setting

```sh
$ yarn add -D husky lint-staged

```

```json
  "scripts": {
    "precommit": "lint-staged"
  },
  "lint-staged": {
    "*.{js,vue}": [
      "yarn lint",
      "git add"
    ]
  },
```


### References

- [How to set up ES Lint for Airbnb, Vue JS, and VS Code](https://medium.com/@agm1984/how-to-set-up-es-lint-for-airbnb-vue-js-and-vs-code-a5ef5ac671e8)
- [Using Prettier and husky to make your commits safe](https://medium.com/@bartwijnants/using-prettier-and-husky-to-make-your-commits-save-2960f55cd351)
