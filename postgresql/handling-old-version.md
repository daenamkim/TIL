# Handling old version PostgreSQL

When I tried to setup old version postgresql with `brew` I used `brew link`.
```
$ brew install postgresql@10
$ brew link --force postgresql@10
$ postgres -V
```

But this way couldn't fix an error as below.

```sh
$ brew services start postgres
Error: Formula `postgresql` is not installed.
$ brew unlink postgresql@10
```

For this problem, I copied the old version to postgresql dir.

```
$ mkdir -p /usr/local/Cellar/postgresql
$ cp -rf /usr/local/Cellar/postgresql\@10/10.6_1 /usr/local/Cellar/postgresql/
$ brew switch postgres 10.6_1
$ postgres -V
```

```
$ pg_ctl -D /usr/local/var/postgres start && brew services start postgres
$ ps | grep postgres
```

Yay!

- [brew link](https://discourse.brew.sh/t/installing-in-cellar/2361)
- [brew switch](https://apple.stackexchange.com/questions/304024/how-do-you-install-an-older-version-of-postgres-9-6-using-homebrew)
