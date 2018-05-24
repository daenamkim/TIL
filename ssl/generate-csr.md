# Generate CSR

There are many reasons for using CSR and I tried to generate CSR for a my wildcard ssl certificate.

```sh
$ openssl req -out CSR.csr -new -newkey rsa:2048 -nodes -keyout privatekey.key
Generating a 2048 bit RSA private key
.........+++
....................................................................+++
writing new private key to 'privatekey.key'
-----
You are about to be asked to enter information that will be incorporated
into your certificate request.
What you are about to enter is what is called a Distinguished Name or a DN.
There are quite a few fields but you can leave some blank
For some fields there will be a default value,
If you enter '.', the field will be left blank.
-----
Country Name (2 letter code) []:JP
State or Province Name (full name) []:Tokyo
Locality Name (eg, city) []:**********
Organization Name (eg, company) []:OOOTOKO
Organizational Unit Name (eg, section) []:
Common Name (eg, fully qualified host name) []:*.oootoko.net
Email Address []:daenam.kim@*****.***
```

And open the CSR generated, copy contents into a certificate configuration setting of the console.

Notice that `privatekey.key` will be used for web server's SSL setting later.

[Source](https://support.globalsign.com/customer/portal/articles/1221018-generate-csr---openssl)
