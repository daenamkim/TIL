# Jest, ReferenceError: localStorage is not defined

I faced an error when I ran `yarn test` to excute Jest(https://facebook.github.io/jest/en/).

So I searched and [clarkbw](https://www.npmjs.com/~clarkbw) had alread done with this issue. Thanks clarkbw.

### Install

```sh
yarn add --dev jest-localstorage-mock
```

### Setup

I added a setting as below in my `package.json`.

```json
...
"jest": {
  ...
  "setupFiles": [
    "<rootDir>/config/polyfills.js",
    "jest-localstorage-mock"
  ],
  ...
```

Then I ran it again and it went away. Cool!

[Source](https://www.npmjs.com/package/jest-localstorage-mock)
