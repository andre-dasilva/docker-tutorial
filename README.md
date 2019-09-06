# Cheatsheet for docker

## List Docker CLI commands
docker
docker container --help

## Display Docker version and info
docker --version
docker version
docker info

## Execute Docker image
docker run hello-world

## List Docker images
docker image ls

## List Docker containers (running, all, all in quiet mode)
docker container ls
docker container ls --all
docker container ls -aq

## Create image using this directory's Dockerfile and add tag friendlyhello
docker build -t friendlyhello .

## Run "friendlyhello" mapping port 4000 to 80
docker run -p 4000:80 friendlyhello  
docker run -d -p 4000:80 friendlyhello

## List all running containers
docker container ls                                
docker container ls -a            

## Stop the specified container
docker container stop <hash>          
docker container kill <hash>

## Remove specified container from this machine
docker container rm <hash>        

## Remove all container
docker container rm $(docker container ls -a -q)

## List all images on this machine 
docker image ls -a

## Remove specified image from this machine
docker image rm <image id>

## Remove all images from this machine
docker image rm $(docker image ls -a -q)   

## Log in this CLI session using your Docker credentials
docker login

## Tag <image> for upload to registry
docker tag <image> username/repository:tag

## Upload tagged image to registry
docker push username/repository:tag

## Run image from a registry
docker run username/repository:tag

## List stacks or apps
docker stack ls                                 

## Run the specified Compose file
docker stack deploy -c <composefile> <appname>

## List running services associated with an app
docker service ls    

## List tasks associated with an app
docker service ps <service>                 

## Inspect task or container
docker inspect <task or container>                   

## List container IDs
docker container ls -q                               

## Tear down an application
docker stack rm <appname>       

## Take down a single node swarm from the manager                     
docker swarm leave --force      
