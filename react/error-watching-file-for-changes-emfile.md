# Error watching file for changes: EMFILE

When I ran `yarn test` to test React App, an error occurred as below.

```sh
2018-04-11 17:43 node[90491] (FSEvents.framework) FSEventStreamStart: register_with_server: ERROR: f2d_register_rpc() => (null) (-22)
events.js:165
      throw er; // Unhandled 'error' event
      ^

Error: Error watching file for changes: EMFILE
    at FSEvent.FSWatcher._handle.onchange (fs.js:1379:9)
Emitted 'error' event at:
    at FSEvent.FSWatcher._handle.onchange (fs.js:1382:12)
error An unexpected error occurred: "Command failed.
Exit code: 1
```

```sh
$ brew install watchman
```

[Source](https://qiita.com/terrierscript/items/6490aa94b32a9e4211ea)
