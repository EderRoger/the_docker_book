# the_docker_book
Docker

# You should know...

Unlike traditional virtualization or paravirtualization technologies,

they do not require an emulation layer or a hypervisor layer to run and instead

use the operating system’s normal system call interface

• Add a file.

• Run a command.

• Open a port.

A Docker container is:
• An image format.

• A set of standard operations.

• An execution environment.

docker start - start a container but not attach to him

docker attach - bind to a container (need press Enter)

docker stop - stop a container

docker stats - statitics to container

docker top  - container process

docker logs (-ft) - logs to run container


What is a Docker image?

Let’s continue our journey with Docker by learning a bit more about Docker im-

ages. A Docker image is made up of filesystems layered over each other. At the

base is a boot filesystem, bootfs , which resembles the typical Linux/Unix boot

filesystem. A Docker user will probably never interact with the boot filesystem.

Indeed, when a container has booted, it is moved into memory, and the boot

filesystem is unmounted to free up the RAM used by the initrd disk image.


A user repository takes the form of a username and a repository name; for example,

jamtur01/puppet .

• Username: jamtur01

• Repository name: puppet

Alternatively, a top-level repository only has a repository name like ubuntu . The

top-level repositories are managed by Docker Inc and by selected vendors who pro-

vide curated base images that you can build upon (e.g., the Fedora team provides

a fedora image). The top-level repositories also represent a commitment from

vendors and Docker Inc that the images contained in them are well constructed,

secure, and up to date.

You can search for images on repository

for instance sudo docker search puppet

Show the last created container - sudo docker ps -l -q


Docker runs a container from the image.

An instruction executes and makes a change to the container.

Docker runs the equivalent of docker commit to commit a new layer.

Docker then runs a new container from this new image.

The next instruction in the file is executed, and the process repeats until all

instructions have been executed.

# Run with volumes -v option

sudo docker run -d -p 9091:80 --name website -v $PWD/website:/var/www/html/website ederrogersouza/nginx nginx

Docker networking

The docker0 interface is a virtual Ethernet bridge that connects our containers and

the local host network.

One end is plugged into the docker0 bridge, and the other end is plugged into the container.

By binding every veth* interface to the docker0 bridge, Docker creates a virtual

subnet shared between the host machine and every Docker container

# command list iptables rules - sudo iptables -t nat -L -n

# Links container.. powerfull

sudo docker run -p 4567 --name webapp --link redis:db -t -i -v $PWD/webapp:/opt/webapp ederrogersouza/sinatra /bin/bash

/etc/hosts file

172.17.0.52	2e66ac7ed88c

127.0.0.1	localhost

172.17.0.51	db aca4724d3f19 redis

172.17.0.52	webapp.bridge

172.17.0.51	redis

172.17.0.51	redis.bridge

172.17.0.41	website

172.17.0.41	website.bridge

172.17.0.52	webapp

You can ping on db ... from the webapp machine.. this is alwesome.. :)

# Docker orchestration
Compose - write in Phyton
Consul - write in Go
Swarm - write in Go

# Swarm and Consul

# TLS Support

# Docker Daemon
