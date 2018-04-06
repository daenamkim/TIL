# Install Docker in Ubuntu 16.04

I extracted information for the fastest way to install Docker the latest version in Ubuntu 16.04.


Update packges and install some packages to use repository over HTTPS

```sh
$ sudo apt-get update
$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
```

Add Docker's GPG key and verify it.

```sh
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
$ sudo apt-key fingerprint 0EBFCD88
```

Set up stable repository for Docker and install it.

```sh
$ sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
$ sudo apt-get update
$ sudo apt-get install docker-ce
```

Verify Docker works.

```sh
$ sudo docker run hello-world
```

[Source](https://docs.docker.com/install/linux/docker-ce/ubuntu/)