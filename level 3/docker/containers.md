

## **Docker Containers and Images**
![enter image description here](https://miro.medium.com/max/1273/1*p8k1b2DZTQEW_yf0hYniXw.png)
## **Docker Containers**
## Containers

Use  `docker container my_command`

`create`  — Create a container from an image.  
`start`  — Start an existing container.  
`run`  — Create a new container and start it.  
`ls`  — List running containers.  
`inspect`  — See lots of info about a container.  
`logs`  — Print logs.  
`stop`  — Gracefully stop running container.  
`kill`  —Stop main process in container abruptly.  
`rm`— Delete a stopped container.

## exemples

## **List all running containers:**

**docker container ls**
     
     (list all containers, running or not): docker container ls -a
    

## **Start a docker container:**

 **Usage: docker start <container name or id>**
    
     Example: docker start foo
    

## **Attach to a docker container:**

**Usage: docker attach <container name or id>**
    
     Example: docker attach foo
    

## **Remove a container:**

 **Usage: docker rm <container name or id>**
    
      Example: docker rm foo
        
    Force remove: docker rm foo -f
    

## **Run a new container:**

  **Usage: docker run <image> <command>**
    
      Example with options: docker run --name=bar -it ubuntu bash
    

## **Remove all containers:**

       docker container ls -aq | xargs docker container rm
