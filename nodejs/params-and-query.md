# Params and Query

In API as below:

```js
app.get('/sample/:id', routes.sample);
```

Let's get some params from a URL.

```sh
'/sample/:id?page=1&limit=10'
```

```js
let id = req.params.id;
let page = req.query.page;
let limit = req.query.limit;
```

[Source](https://expressjs.com/en/api.html)
[Source](https://stackoverflow.com/questions/6912584/how-to-get-get-query-string-variables-in-express-js-on-node-js)
