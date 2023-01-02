## **HONEST WARNING**

**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._

# DOCKER

## File Example:

```dockerfile
 appserver:
   build:
      context: .
      dockerfile: app/Dockerfile-dev
   image: atsea_app
   ports:
     - "8080:8080"
     - "5005:5005"
   networks:
     - front-tier
     - back-tier
   secrets:
     - postgres_password

secrets:
 postgres_password:
   file: ./devsecrets/postgres_password

networks:
  front-tier:
  back-tier:
 ```

## Useful commands:

* ```docker build .```    Build docker image (```docker build -f Build_Dockerfile -t build-env```)
* ```docker ps``` Display currently running docker images … (useful if you want know container id to stop it
* ```docker stop (containerId)``` stops docker instance
* ```docker run landoop/fast-data-dev``` running Kafka and other services that Kafka needs
* ```docker system prune -a``` Remove all unused containers and so on.
* ```docker restart $(docker ps -aq)``` it restarts all dockers containers
* ```docker rm $(docker ps -aq)```   It deletes all containers
* ```docker rmi $(docker images -q)``` It deletes all images
* ```docker stop $(docker ps -aq)```  stop all containers
* ```docker-compose -f docker/local-env.yml up -d```run specified docker file in background
* ```docker commit [CONTAINER_NAME] [IMAGE_NAME]``` - Building an Image from a Container Volumes
* ```docker volume inspect [VOLUME_NAME]``` - if you need to view various details about a volume that you created.

## TIPS & TRICKS:

* To increase the build’s performance, exclude files and directories by adding a .dockerignore file to the context
  directory.
* Do not use your root directory, /, as the PATH as it causes the build to transfer the entire contents of your hard
  drive to the Docker daemon.
* Whenever possible, Docker will re-use the intermediate images (cache), to accelerate the docker build process
  significantly. This is indicated by the Using cache message in the console output.
* The PATH is a directory on your local filesystem.
* The URL is a Git repository location.
* Lines that begin with # as a comment, unless the line is a valid parser directive. A # marker anywhere else in a line
  is treated as an argument.
* There are four key Docker concepts at play: images, layers, the Dockerfile, and the Docker cache.Dockerfile describes
  how to build the Docker image. An image consists of a number of layers. The Dockerfile starts with a base image and
  adds additional layers. A new layer is generated when new content is added to the image. Each layer that is built is
  cached so it can be re-used on subsequent builds. When a Docker build runs, it will re-use any existing layers that it
  can from the cache. This reduces the overall time and space needed for each build. Anything that has changed, or has
  not been built before, will be built as needed.
* The order and contents of the layers matter.
* Since Java 10, you can specify how much memory JVM will use depending on container memory.-XX:MaxRAMPercentage=75.0
  means JVM won't use more than 75% of a container memory.
* Docker Volumes to containers will allow some of the data in your container to persist across image rebuilds.docker
  Volumes allow some of the data in your

## TOOLS

* https://github.com/wagoodman/dive

## TODO

* http://javarevisited.blogspot.co.uk/2013/05/10-hibernate-interview-questions-answers-java-j2ee-senior.html
* http://www.java67.com/2016/02/top-20-hibernate-interview-questions.html
