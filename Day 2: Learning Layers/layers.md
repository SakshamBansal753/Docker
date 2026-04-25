## Input
```
bash
to pull mysql
docker pull mysql

to pull version
docker pull mysql :8.0

detach mode container
docker run -d (IMAGE_NAME) #default attach mode This runs the container in the background.

If you want to set some enve variable attach with your containier use -e
docker run -d -e MYSQL_ROOT_PASSWORD=secret mysql

To give custom name for your containier use --name
docker run -d -e MYSQL_ROOT_PASSWORD=secret --name mysql-saksham mysql


```
# Layers
1) Container <br>
       ⬆️
2) layer Stack<br>
       ⬆️
3) base layer
when we create a new container ,a new writable layer(called container layer ) is added on top of underlying layers
other are readable immutable layers

# Port Binding
A container has its own internal network. By default, its ports are not accessible from your system.
so what we do here we generally map our port to our container using below command
 ```
bash
port binding command
                map
host port----------------->container port

# if port is already binded you can,t rebind that port untill you delete that container 
docker run -d -e MYSQL_ROOT_PASSWORD=secret --name mysql-saksham -p8000:3306 mysql

```
# Trouble shoot commands
To check error in container we can use trouble shoot commands in our terminal
```
bash
#to get all logs for container with id to check errors
docker logs CONT_ID/NAME

# to run additaional command on our runing container we can use exec command
docker exec -it CONT_ID /bin/bash
```
# Docker vs VM
Application Layer<br>
⬆️<br>
Host OS Kernel<br>
⬆️<br>
hardware

## Docker vs Virtual Machine (VM)

| Feature            | Docker (Containers)                                  | Virtual Machine (VM)                              |
|--------------------|------------------------------------------------------|--------------------------------------------------|
| Architecture       | Uses host OS kernel                                  | Uses hypervisor + separate guest OS              |
| OS Requirement     | No separate OS per container                         | Each VM has its own OS                           |
| Startup Time       | Very fast (seconds)                                  | Slow (minutes)                                   |
| Resource Usage     | Lightweight                                          | Heavy (more CPU, RAM, storage)                   |
| Size              | Small (MBs)                                           | Large (GBs)                                      |
| Isolation          | Process-level isolation                              | Full OS-level isolation                          |
| Performance        | Near-native                                          | Slightly slower                                  |
| Portability        | High (runs anywhere with Docker)                     | Moderate                                         |
| Security           | Moderate (shared kernel)                             | Strong (isolated OS)                             |
| Deployment         | Simple and fast                                      | More complex                                     |
| Use Cases          | Microservices, CI/CD, cloud-native apps              | Legacy apps, different OS needs, full isolation  |
| Example            | Run MySQL instantly using Docker                     | Install OS + MySQL manually                      |

docker is initially built for linux and it  cause problem as most images are linux kernel based to resolve problem to use them on other os 
here help ** Docker dekstop ** as it act a lightweight hyperisor uses a lightweight linux vm or linux supervisor
that's why preffered linux or ubuntu  but if not good to use for windows or other os as well as 

# please it is all written by me not by any AI
