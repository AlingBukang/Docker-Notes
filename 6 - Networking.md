Networks:
- bridge - default(standalone that communicates with other containers)
- host - standalone that doesn't need isolation between the container and the host
- none - isolated container that doesn't need to communicate with other container or external network

`docker run --network=[network-type] [container]`

# list networks
docker network ls
# create user defined networks
docker network create --driver bridge --subnet [CIDR-range] --gateway [gateway-ip] [network-name]

Reference:
https://docs.docker.com/network/