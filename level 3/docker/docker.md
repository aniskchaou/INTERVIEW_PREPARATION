
## Docker

**Docker permet d'embarquer une application dans un ou plusieurs containers logiciels qui pourra s'exécuter sur n'importe quel machine, qu'il soit physique ou virtuel.** 
![Related image](http://www.ourdrives.com:88/static/posts/docker_steps.png)
## But

C'est une technologie qui **a pour but de faciliter les déploiements d'application, et la gestion du dimensionnement de l'infrastructure sous-jacente.** 
![Image result for docker vs virtualization](https://www.aquasec.com/wiki/download/attachments/2854029/docker-birthday-3-intro-to-docker-slides-18-638.jpg?version=1&modificationDate=1515522843003&api=v2)
Les containers sont une méthode de virtualisation de système d’exploitation permettant de lancer une application et ses dépendances à travers un ensemble de processus isolés du reste du système. Cette méthode **permet d’assurer le déploiement rapide et stable des applications** dans n’importe quel environnement informatique.
## Quels sont les principaux services et technos Docker ?

### 1. Docker Hub

Docker met à la disposition des développeurs un service en ligne, baptisé le  Docker Hub, **conçu pour faciliter l'échange d'applications containérisées.** 

Hébergeant plus de 100 000 images de containers, cet espace est aussi intégré à GitHu

 
### 2. Docker Compose

Docker Compose est un outil développé par Docker pour créer les architectures logicielles containérisées. Dans cette logique, chaque brique de l'application (code, base de données, serveur web...) sera hébergée par un container. Cet outil repose sur le langage YAML (pour Yet Another Markup Language) pour décrire l'architecture. Une fois celle-ci codée dans un fichier YAML, l'ensemble des services applicatifs seront générés via une commande unique.



### 3. Docker Swarm et Kubernetes

Pour faciliter le management des architectures complexes, Docker à construit une plateforme de **Containers-as-a-Service**. Baptisée  Docker Enterprise, elle comprend les principaux outils nécessaires **pour gérer le déploiement, le pilotage, la sécurité et le monitoring de tels environnements.** 
![Image result for docker swarm](https://clouding.io/kb/wp-content/uploads/2018/08/KB-Swarm-Diagrama.png)
Côté gestion de cluster,  **Docker Entreprise intègre à la fois Swarm, son moteur d'orchestration maison, mais aussi Kubernetes, qui s'est imposé comme un standard dans la management de cluster.** 




## Commandes


## Containers

Use  `docker container my_command`

`create`  — Create a container from an image.  
`start` — Start an existing container.  
`run`  — Create a new container and start it.  
`ls`  — List running  containers.  
`inspect`  — See lots of info about a container.  
`logs`  — Print logs.  
`stop`  — Gracefully stop running container.  
`kill`  —Stop main process in container abruptly.  
`rm`— Delete a stopped container.

## Images

Use  `docker image my_command`

`build` — Build an image.  
`push`  — Push an image to a remote registry.  
`ls`  — List images.  
`history`  — See intermediate image info.  
`inspect`  — See lots of info about an image, including the layers.  
`rm`  — Delete an image.

## Misc

`docker version`  — List info about your Docker Client and Server versions.  
`docker login` — Log in to a Docker registry.  
`docker system prune`  — Delete all unused containers, unused networks, and dangling images.

## Exemple
1. **docker –version**

This command is used to get the currently installed version of docker

![Docker_Version - Docker Commands - Edureka](https://www.edureka.co/blog/wp-content/uploads/2017/11/Docker_Version-Docker-Commands-Edureka-3-e1510653973130.png)

2. **docker pull**

**Usage: docker pull <image name>**

This command is used to pull images from the  **docker repository**(hub.docker.com)

![Docker_Pull - Docker Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/11/Docker_Pull-Docker-Commands-Edureka-2-e1510653950923.png)  
  
3.  **docker run**

**Usage: docker run -it -d <image name>**

This command is used to create a container from an image

![docker_run - Docker Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/11/docker_run-Docker-Commands-Edureka-e1510653910376.png)
.  **docker ps -a**

This command is used to show all the running and exited containers

![docker_psa - Docker Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/11/docker_psa-Docker-Commands-Edureka-e1510653854892.png)
6.  **docker exec**

**Usage: docker exec -it <container id> bash**

This command is used to access the running container

![docker_exec - Docker Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/11/docker_exec-Docker-Commands-Edureka-e1510653829237.png)  
  
7.  **docker stop**

**Usage: docker stop <container id>**

This command stops a running container

![docker_stop - Docker Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/11/docker_stop-Docker-Commands-Edureka-e1510653793521.png)  
  
8.  **docker kill**

**Usage: docker kill <container id>**

This command kills the container by stopping its execution immediately. The difference between ‘docker kill’ and ‘docker stop’ is that ‘docker stop’ gives the container time to shutdown gracefully, in situations when it is taking too much time for getting the container to stop, one can opt to kill it

![docker_kill - Docker Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/11/docker_kill-Docker-Commands-Edureka-e1510653772661.png)  
  
9.  **docker commit**

**Usage: docker commit <conatainer id> <username/imagename>**

This command creates a new image of an edited container on the local system

![docker_commit - Docker Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/11/docker_commit-Docker-Commands-Edureka-e1510653734760.png)
10.  **docker login**

This command is used to login to the docker hub repository
![docker_login - Docker Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/11/docker_login-Docker-Commands-Edureka-1-e1510653706645.png)
11. **docker push**

**Usage: docker push <username/image name>**

This command is used to push an image to the docker hub repository

![docker_push - Docker Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/11/docker_push-Docker-Commands-Edureka-e1510653678749.png)  
  
12.  **docker images**

This command lists all the locally stored docker images

![docker_images - Docker Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/11/docker_images-Docker-Commands-Edureka-e1510653647888.png)  
  
13.  **docker rm**

**Usage: docker rm <container id>**

This command is used to delete a stopped container

![docker_rm - Docker Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/11/docker_rm-Docker-Commands-Edureka-e1510653622699.png)  
  
14.  **docker rmi**

**Usage: docker rmi <image-id>**

This command is used to delete an image from local storage

![docker_rmi - Docker Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/11/docker_rmi-Docker-Commands-Edureka-e1510653592230.png)  
  
15.  **docker build**

**Usage: docker build <path to docker file>**

This command is used to build an image from a specified docker file

![docker_build - Docker Commands - Edureka](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/11/docker_built-Docker-Commands-Edureka-e1510653559161.png)

[](https://www.edureka.co/docker-training)