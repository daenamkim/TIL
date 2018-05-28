# SSH Connection

In order to generate a SSH key for a Jenkins user in the server.

```sh
$ sudo su - jenkins
```

Generate the SSH key.

```
$ ssh-keygen -t rsa -b 4096 -C "daenam.kim@gmail.com"
Generating public/private rsa key pair.
Enter file in which to save the key (/var/lib/jenkins/.ssh/id_rsa): <= TYPE NOTHING
Enter passphrase (empty for no passphrase): <= TYPE NOTHING
Enter same passphrase again: <= TYPE NOTHING
Your identification has been saved in /var/lib/jenkins/.ssh/id_rsa.
Your public key has been saved in /var/lib/jenkins/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:77MaR29p3dc ... NP//yih4RGvjAHWa+jE daenam.kim@gmail.com
The key's randomart image is:
+---[RSA 4096]----+
|                 |
|        o .+     |
|       = B. =.   |
|      + = +..o.  |
|       oSo.o  o. |
|      . Eo=. + oo|
|       ..@+.* . =|
|        ++*=.o  o|
|        .o+*. o.o|
+----[SHA256]-----+
```

Confirm, copy a public key into [GitHub SSH and GPG keys](https://github.com/settings/keys).

```sh
$ cat .ssh/id_rsa.pub
ssh-rsa AAAAB3NzaC ... VUxQ== daenam.kim@gmail.com
```

Do a connection test and get

```sh
$  ssh -T git@github.com
The authenticity of host 'github.com (192.30.255.112)' can't be established.
RSA key fingerprint is SHA256:nThbg6kXUpJWGl ... CARLviKw6E5SY8.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added 'github.com,192.30.255.112' (RSA) to the list of known hosts.
Hi daenamkim! You've successfully authenticated, but GitHub does not provide shell access.
```

If you confirmed "Hi daenamkim! You've successfully authenticated, but GitHub does not provide shell access." then SSH connection was successful.

- [Source](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)
- [Source](https://help.github.com/articles/testing-your-ssh-connection/)
