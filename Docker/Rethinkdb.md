# Guide

[Rethinkdb](https://www.rethinkdb.com/)

## Installation

*   Setup your VM, install your vmware. Default to using Bridge.
*   Install Docker

```js
sudo curl -sSL https://gist.githubusercontent.com/sirkkalap/e87cd580a47b180a7d32/raw/d9c9ebae4f5cf64eed4676e8aedac265b5a51bfa/Install-Docker-on-Linux-Mint.sh | bash -x
```

*   Update the VM

```js
sudo apt-get update
```

*   Install Jenkins (Note that Jenkins 2.0 is not LTS yet,
    so no docker image for it)

```js
sudo docker pull rethinkdb
```

*   Port forward Rethinkdb services.

```js
docker run -p 8080:8080 -p 28015:28015 -d rethinkdb
```

## Links

[Official Rethinkdb Image](https://hub.docker.com/_/rethinkdb/)

## Additional

*   IP address:8080 will get you to Rethinkdb console.
