# gyp ERR!

If you faced error as below you can try this as an one of options

```sh
$ yarn

...

gyp ERR! build error
gyp ERR! stack Error: `make` failed with exit code: 69
gyp ERR! stack     at ChildProcess.onExit (/Users/daenamkim/.nvm/versions/node/v10.16.0/lib/node_modules/npm/node_modules/node-gyp/lib/build.js:262:23)
gyp ERR! stack     at ChildProcess.emit (events.js:198:13)
gyp ERR! stack     at Process.ChildProcess._handle.onexit (internal/child_process.js:248:12)
gyp ERR! System Darwin 19.0.0
gyp ERR! command "/Users/daenamkim/.nvm/versions/node/v10.16.0/bin/node" "/Users/daenamkim/.nvm/versions/node/v10.16.0/lib/node_modules/npm/node_modules/node-gyp/bin/node-gyp.js" "rebuild"
gyp ERR! cwd /Users/daenamkim/Developments/workspace/curvegrid/multibaas/web/node_modules/sha3
```

Run following commands

```sh
$ sudo xcode-select --switch /Applications/Xcode.app
$ sudo xcodebuild -license
```

and run `yarn`

```sh
$ yarn
yarn install v1.17.3
[1/4] 🔍  Resolving packages...
[2/4] 🚚  Fetching packages...
...
[4/4] 🔨  Building fresh packages...
✨  Done in 15.25s.

```

[Reference](https://qiita.com/UTA6966/items/6f8b1fd21c2dc9591488)
