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

