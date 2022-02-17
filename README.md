## part12
https://fullstackopen.com/en/part12

### Containers

In this part we focused on containers and how to work with them using [Docker](https://www.docker.com/). A [key benefit](https://www.infoworld.com/article/3310941/why-you-should-use-docker-and-containers.html) of containers is creating immutable execution environments that ultimately speeds up the development lifecycle by eliminating bugs related to differing environment conditions. Containers are [considered to be](https://docs.microsoft.com/en-us/virtualization/windowscontainers/about/containers-vs-vm) lightweight when compared to virtual machines, this is because containers provide OS-level virtualization whilst VMs virtualize the OS first which is more resource intensive.

We began by learning the basics of the [Docker CLI](https://docs.docker.com/engine/reference/run/) relating to images and containers. We then moved on to learning to use [Docker-compose](https://docs.docker.com/compose/) to run multiple containers at the same time. ```todo-app``` and ```phonebook``` are web apps that I made containerized development and production environments for, using docker-compose and applying [best practices](https://snyk.io/blog/10-best-practices-to-containerize-nodejs-web-applications-with-docker/) where possible. This included using [volumes](https://docs.docker.com/storage/volumes/) and [bind mounts](https://docs.docker.com/storage/bind-mounts/), setting up and configuring [MongoDB](https://www.mongodb.com/) and [Redis](https://redis.io/) database services and an nginx [reverse proxy](https://www.nginx.com/resources/glossary/reverse-proxy-server/) server. We also used the [multi-stage build](https://docs.docker.com/develop/develop-images/multistage-build/) functionality to add a testing step before building and serving the frontend as found in ```todo-app/todo-frontend/Dockerfile```.

- hello-front
   - Basic [CRA](https://create-react-app.dev/) hello world app. The Dockerfile builds an image that, when run, creates a container that serves the built app [using nginx](https://hub.docker.com/_/nginx).
- phonebook/todo-app
  - Phone directory/Todo app. Both frontends are built with CRA and the backends are built in Node with Express.