### Input
```
bash
# Check if Docker is installed
docker -v

# Check detailed Docker version info
docker version

# Pull a Docker image from Docker Hub
docker pull hello-world

# List all Docker images
docker images

# To create container
docker run hello-world
```
### Output
Hello from Docker!
This message shows that your installation appears to be working correctly.

### Steps taken by daemon to generate this text
To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.
```
bash
# If you want to run and reate container together
docker run -it ubuntu bash   # -it means interactive

# To check all files in container
ls

# To create new directory
mkdir saksham

# To check env
env

# To exit container
exit

# To check all containers on docker
docker ps -a  # a for all

# To check active container
docker ps

# To start any deactive container run
docker start (container name or container id)

# To stop container
docker stop (container naem or id)

# To remove image
docker rmi (name or id)

# But first you have to delete that  runing container
docker rm name or id
