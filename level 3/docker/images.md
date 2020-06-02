## **Docker Images**

Use  `docker image my_command`

`build`  — Build an image.  
`push`  — Push an image to a remote registry.  
`ls`  — List images.  
`history`  — See intermediate image info.  
`inspect`  — See lots of info about an image, including the layers.  
`rm`  — Delete an image.
## **Remove a docker image:**

**Usage: docker image rmi <image id>**
    
 

    Example (only uses first 3 characters of image id): docker rmi 70b
    

## **Remove all images:**

       docker image ls -aq | xargs docker rmi -f
    

## **Search for a docker image on dockerhub:**

 **Usage: docker search <image>**
    
     Example: docker search ubuntu
    

## **List docker images:**

       docker image ls
    

## **Build a Docker image:**

   **Usage: docker build <path>**
    
       Example (also tags and names the build): docker build . -t org/serve:0.0.0
    

## **Dockerfiles**

**Specify a base image:**

**Usage: FROM <base image>**
    
      Example: FROM node:latest
    

## **Set a working directory for the container:**

**Usage: WORKDIR <dir>**
    
 Example: WORKDIR /usr/src/app
    

## **Run a command for the container image:**

 **Usage: RUN command**
    
     Command: RUN npm install -g serve
    

## **Copy files into the container:**

-   Usage: COPY <local files/directories> <container files/directories>
    
-   Example: COPY ./display ./display
    
## **Specify a default command for the container:**

-   Usage (shell format): CMD <default command>
    
-   Example: CMD serve ./display
    
-   Usage (exec format,  _recommended_): CMD [“default command”, “arguments”]
    
-   Example: CMD [“node”, “server.js”]