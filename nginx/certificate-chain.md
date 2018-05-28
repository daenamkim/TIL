# Certificate Chain

```sh
$ cat www.example.com.crt bundle.crt > www.example.com.chained.crt
```

```conf
server {
    listen              443 ssl;
    server_name         www.example.com;
    ssl_certificate     www.example.com.chained.crt;
    ssl_certificate_key www.example.com.key;
    ...
}
```

[Source](http://nginx.org/en/docs/http/configuring_https_servers.html)
