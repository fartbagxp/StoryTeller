# Guide

Simple instruction guide on setting up a VM with a Docker container containing
Jenkins.

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
sudo docker pull jenkins
```

*   Port forward Jenkin services.

```js
sudo docker run -p 8080:8080 -p 50000:50000 jenkins
```

## Plugins

[Git Builder plugin](https://wiki.jenkins-ci.org/display/JENKINS/GitHub+pull+request+builder+plugin)

## Links

[Official Jenkins Docker](https://hub.docker.com/_/jenkins/)

## Additional

*   IP address:8080 will get you to Jenkins console.
