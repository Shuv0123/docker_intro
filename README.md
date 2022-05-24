# Docker

## Micorseverces Architecture vs Monolithlic Architecture

- A monolithic application is built as a single and indivisible unit. Usually, such a solution comprises a client-side user interface, a server side-application, and a database

- A Microservices architecture breaks it down into a collection of smaller independent units. These units carry out every application process as a separate service. So all the services have their own logic and the database as well as perform the specific functions.


## What is containerisation
Containerisation is a form of operating system virtualization, through which applications are run in isolated user spaces called containers, all using the same shared operating system (OS).

### Benefits:

- Portability: A container creates an executable package of software that is abstracted away from (not tied to or dependent upon) the host operating system, and hence, is portable and able to run uniformly and consistently across any platform or cloud.
- Speed: Containers are often referred to as “lightweight,” meaning they share the machine’s operating system (OS) kernel and are not bogged down with this extra overhead.
- Fault Isolation: Each containerized application is isolated and operates independently of others. The failure of one container does not affect the continued operation of any other containers.
- Ease of management: Container orchestration platforms can ease management tasks such as scaling containerized apps, rolling out new versions of apps, and providing monitoring, logging and debugging, among other functions. e.g Kubernetes

## What is docker
- Docker is an open-source platform for developing, shipping, and running applications
- It enables us to separate applications from the infrastructure
- It delivers software faster

## Container lifecycle
- Create phase
  - In the create phase, a docker container is created from a docker image
  - `docker create --name <name-of-container> <docker-image-name>`
- Running phase
  - In the running phase, the docker container starts executing the commands mentioned in the image. To run a docker container, use the docker run command.
  - `docker run <container-id>`
- Paused phase/unpause phase
  - In the paused phase, the current executing command in the docker container is paused. Use the docker pause command to pause a running container
  - `docker pause container <container-id or container-name>`
- Stopped phase
  - In the stop phase, the container’s main process is shutdown gracefully. Docker sends SIGTERM for graceful shutdown, and if needed, SIGKILL, to kill the container’s main process
  - `docker stop <container-id or container-name>`
- Killed phase
  - In the kill phase, the container’s main processes are shutdown abruptly. Docker sends a SIGKILL signal to kill the container’s main process.
  - `docker kill <container-id or container-name>`

## Docker vs VM
- Docker is lightweight and user-friendly
- Docker shares the resources of OS as opposed to using the OS completely
- Docker engine connects the container with the OS and only uses the resources required
- VM works with Hypervisor to connect guest OS/VM with Host OS


## Docker commands
- `Docker images`: Will present the images available
- `Docker ps`: To check the containers running
- `Docker ps -a`: To check every container running including hidden files
- `Docker pull`: to pull the image from docker hub
- `Docker run`: to run the image live directly from dockerhub
- `docker exec -it [container id] bash`: to access the running container
- `docker stop`: stops a running container
- `docker kill`: kills container by stopping execution. stop gives time to shut down gracefully
- `docker commit [container id][username/imagename]`: creates new image of an edited container on local system
- `docker rm [container id]`:removes container
- `docker history [image name]`: to view history
- `docker image rm [image name]`: deletes image

### Making docker docs available on our localhost
- `docker run -d -p 4000:4000 docs/docker.github.io`

### enter docker container
- `docker exec -it <container-id/name> sh` bash can also be used instead of sh

### Port mapping in our containers with localhost
- `docker run -d -p localhost-port:container-port`

### Copying files to container
- `docker cp <file to copy> <container_id>:path/to/file` i used docker `cp <file to copy> <container_id>://usr/nginx/html`

### docker commit
- `docker commit <container_id> smia/repo_name`
- `docker push smia/repo_name`



