# Getting Started with Create React App

## Docker commands

#### build the image

`docker build -t react-app .`

#### run the server

`docker run -p 3000:3000 react-app npm start`

#### run the image in shell

`docker run -it react-app sh`

#### get current user

`whoami`

#### view docker images

`docker images`

#### build with tag

`docker build -t react-app:1 .`

#### tag after

`docker image tag react-app:latest react-app:1`

#### tag to latest

`docker image tag react-app:1 react-app:latest`

#### build, tag and push image to docker hub

``` bash
docker build -t react-app:3 .
docker image tag react=app:3 artofthesystem/react-app:3
docker push artofthesystem/react-app:3
```

#### save to a tar file

`docker image save -o react-app.tar react-app:3`

#### remove docker image

`docker image rm <image_name or image_id>`

#### load from a file from tar file

`docker image load -i react-app.tar`

#### run detached mode

`docker run -d react-app`

#### run detached mode with name

`docker run -d --name blue-sky-app react-app`

#### logs

`docker logs <container_id>`
`docker logs -n 5 -t 6fd9b06b36ed`

number of lines to tail (-n 5) and include timestamp (-5)

`docker run -d -p 3000:3000 --name c1 react-app`

#### execute commands against a runnign conatiner

`docker exec c1 ls`
`docker exec -it c1 sh`

#### stop a container

`docker stop <container_name> or <container_id>`

#### start a container

`docker start <container_name> or <container_id>`

#### docker volumes

#### create

`docker volume create <volume_name>`

#### inspect

`docker volume inspect <volume_name>`

`docker run -d -p 4000:3000 -v app-data:/app/data react-app`
`docker exec -it 706 sh`

#### Copy a file from container to host

`docker cp <container_id>:/app/log.txt .`

#### Copy a file from host to container

`echo hello > file.txt`
`docker cp file.txt <container_id>:/app`

#### Mapping to local file directory

`docker run -d -p 5001:3000 -v $(pwd):/app react-app`

##### With another volume:

`docker run -d -p 5001:3000 -v $(pwd):/app -v app-data:/app/data react-app`

#### Remove all containers (inc. running ones)

`docker container rm -f $(docker container ls -aq)`

#### Remove all images

`docker image rm -f $(docker image ls -q)`