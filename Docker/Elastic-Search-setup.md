# Guide

This is a simple instruction for setting up a VM with a Docker container containing Elastic Search / Kibana.

## Installation

This is a set of instructions to setup a VM loaded with Mint Linux 17.3 with a Docker container with Elastic search / Kibana installation.

1) Setup your VM, install your vmware. Default to using NAT.

2) Install prerequisites for Docker according to [this](https://docs.docker.com/engine/installation/linux/debian/#debian-jessie-80-64-bit) (just the first half of the link).

3) Install Docker:
```js
		sudo wget -qO- https://get.docker.com/ | sh
```

4) Test out your Docker setup:
```js
	sudo docker run hello-world
```

5) Install Elastic Search / Kibana image:
```js
	docker pull nshou/elasticsearch-kibana
```

6) Up and running:

- Ensure it is running by command
```js
  docker ps
```

- Connect to Kibana on localhost:5601.


## Links

Link for [Elastic search / Kibana image](https://hub.docker.com/r/nshou/elasticsearch-kibana/).

## Additional

If VM is using NAT, figure out what IP your VM is using by running ifconfig and looking at eth0.
- IP address:5601 will get you to Kibana.
- IP address:9200 will get you to Elastic Search.
