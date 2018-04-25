# Switch a Package Version

When I ran a command, I faced an error as below.

```sh
$ yarn add gojs
yarn add v1.5.1
[1/4] 🔍  Resolving packages...
[2/4] 🚚  Fetching packages...
error upath@1.0.4: The engine "node" is incompatible with this module. Expected version ">=4 <=9".
error An unexpected error occurred: "Found incompatible module".
...
```

Then I checked a node version.

```sh
$ node -v
v10.0.0
```

OK, simply rollback a node version.
I use a [brew](https://brew.sh/) so do like this.

```sh
$ brew info node
node: stable 9.11.1 (bottled), HEAD
Platform built on V8 to build network applications
https://nodejs.org/
/usr/local/Cellar/node/9.7.1_1 (5,125 files, 49.7MB)
  Poured from bottle on 2018-03-07 at 07:00:25
/usr/local/Cellar/node/9.8.0 (5,125 files, 49.7MB)
...

$ brew switch node 9.11.1
...

$ brew link --overwrite node
Linking /usr/local/Cellar/node/9.11.1... 140 symlinks created

$ node -v
v9.11.1

$ yarn add gojs
...
success Saved lockfile.
success Saved 1 new dependency.
info Direct dependencies
└─ gojs@1.8.17
info All dependencies
└─ gojs@1.8.17
✨  Done in 8.68s.
```

Good.
