# Show Packages List

## in npm

for global packages.

```sh
$ npm list -g --depth=0
```

for local packages.

```sh
$ npm list --depth=0
```

If I don't use `--depth=0` together, all dependencies will be shown.

## in yarn

for global packages.

```sh
$ yarn global list
```

for local packages.

```sh
$ yarn list --depth=0
```

[node.js - How to list npm user-installed packages?](https://stackoverflow.com/questions/17937960/how-to-list-npm-user-installed-packages)
[yarn global](https://yarnpkg.com/lang/en/docs/cli/global/)

