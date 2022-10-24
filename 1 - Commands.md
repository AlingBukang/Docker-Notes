**help**
```sh
docker --help
docker --version
```

```sh
# list containers
docker ps
docker ps -a

# stop container
docker stop [container-id/name]

# delete container
docker rm [container-id/name]

# list images
docker images

# delete image
docker rmi [image-id/name]

# download image for later use
docker pull [image-name]:[tag]

# remove dangling images
docker image prune -a
```

**Run container**
```sh
# run a container with specific image version aka tag
docker run [container]:[tag]

# run container with remote docker engine
docker -H=[remote-docker-engine-IP:port] run [container]:[tag]

# assign a container name
docker run --name=[my-container-name] [docker-image]

# run container with terminal and interactive
docker run -it [container]

# dettach container aka running in background
docker run -d [container-id/name]

# reattach container
docker attach [container-id/name]

# run container with command
docker run [container] [command] 

# run container with specified user
docker run [container] [command] -u [user]

# map host:container port
docker run -p [host-port]:[container-port] [container]

# execute a command on a running container
docker exec [container-id/name] [command]

ex. 'docker exec 264 cat /etc/*release*'

# access the container via shell
docker exec -it [container-name] /bin/sh

# view config
docker inspect [container-id/name]

# view logs
docker logs [container-id/name]

# specify env variables
docker run -e ENVIRONMENT=dev -p 80:80 [container]

# link containers
docker run -d --name=redis-container redis

docker run -d -p 80:80 --name=webapp-container --link redis-container:redis-container webapp

# specify cpu(%) and memory(mb)
docker run --cpus=.5 ubuntu
docker run --memory=100m ubuntu
```

**Volumes**
```sh
# volumes - this will create a dir on the host
docker volume create [volume-name]

# inspect volume
docker volume inspect [volume-name]

# volume mount - stores data on the host for later use
docker run -dp 80:80 -v [volume-name]:/container-dir [container]

# bind mount - store data in a non-volume storage, e.g. external storage
docker run -dp 80:80 -v /host-dir:/container-dir [container] 

# alternative bind mounting
docker run --mount type=bind,source=/host-dir,target=/container-dir [container] 
```

**Network**
```sh
# network
docker run --network=[network-type] [container]

# list networks
docker network ls

# create user defined networks
docker network create --driver bridge --subnet [CIDR-range] [network-name]
```

**Registry**
```sh
# Deploy image to privately hosted registry
docker run -dp 5000:5000 --name registry registry:2

# pull source image
docker pull [source-image]

# tag image
docker image tag [source-image] localhost:5000/[target-image]

# push image
docker push localhost:5000/[target-image]

# check the list of images pushed
curl -X GET localhost:5000/v2/_catalog
```