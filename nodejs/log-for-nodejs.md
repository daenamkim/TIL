# Log for Express

The simplest way to log for access logs of express.

Install a `morgan`.

```sh
$ yarn add morgan
yarn add v1.6.0
[1/4] 🔍  Resolving packages...
[2/4] 🚚  Fetching packages...
[3/4] 🔗  Linking dependencies...
[4/4] 📃  Building fresh packages...
success Saved lockfile.
success Saved 3 new dependencies.
info Direct dependencies
└─ morgan@1.9.0
info All dependencies
├─ basic-auth@2.0.0
├─ morgan@1.9.0
└─ on-headers@1.0.1
✨  Done in 0.96s.
```

Add some codes.

```javascript
const morgan = require('morgan');
...
app.use(morgan('dev'));
...
```

Run.

```sh
$ node index.js
GET /v0/topic-model 200 1004.787 ms - 472
OPTIONS /v0/topic-model/1/download 204 0.090 ms - 0
```

Done.

[morgan - npm](https://www.npmjs.com/package/morgan)
