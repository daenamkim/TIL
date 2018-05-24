# SSL Setting

## Listen both 80 and 443

I'm using virtual host settings so I modified the one of them as below.

```conf
server {
    listen 80;
    listen 443 ssl;
    server_name jenkins.oootoko.net;
    ssl_certificate /etc/nginx/ssl/wildcard.oootoko.net.crt;
    ssl_certificate_key /etc/nginx/ssl/wildcard.oootoko.net.key;
    ...
}
```

[Source](http://nginx.org/en/docs/http/configuring_https_servers.html#single_http_https_server)

## Redirect 80 to 443

```conf
server {
    listen 80;
    listen [::]:80;
    server_name oootoko.net;
    return 301 https://$host$request_uri;
}

server {
    listen 443 ssl;
    listen [::]:443 ssl;
    server_name oootoko.net;
    ssl_certificate /etc/nginx/ssl/wildcard.oootoko.net.crt;
    ssl_certificate_key /etc/nginx/ssl/wildcard.oootoko.net.key;
    ...
}
```

[Source](https://www.digitalocean.com/community/questions/best-way-to-configure-nginx-ssl-force-http-to-redirect-to-https-force-www-to-non-www-on-serverpilot-free-plan-by-using-nginx-configuration-file-only)

## Common Issue

If an error ocurred as below then `private key`(was created by generating CSR.) must be wrong.

```sh
2018/05/23 18:43:02 [emerg] 12426#12426: SSL_CTX_use_PrivateKey_file("/etc/nginx/ssl/wildcard.oootoko.net.key") failed (SSL: error:0906D06C:PEM routines:PEM_read_bio:no start line:Expecting: ANY PRIVATE KEY error:140B0009:SSL routines:SSL_CTX_use_PrivateKey_file:PEM lib)
```

Just check all out if the certificate and the key are OK or not.

```sh
$ openssl x509 -noout -text -in your.crt
$ openssl rsa -noout -text -in your.key
```

[Source](https://snippets.aktagon.com/snippets/543-how-to-fix-pem-read-bio-no-start-line-error-nginx-error)
