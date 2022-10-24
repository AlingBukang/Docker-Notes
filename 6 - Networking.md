**Networks:**
- **bridge** - default(standalone/isolated containers that communicate with other containers within the host); internal private network
- **host** - standalone containers that don't need isolation among other containers and the host; unique port per container
- **none** - isolated container that doesn't need to communicate with other container or external network


> docker run --network=[network-type] [container]

**list networks**
> docker network ls

**create user defined networks**
> docker network create --driver bridge --subnet [CIDR-range] --gateway [gateway-ip] [network-name]


**Overlay Network**
Use overlay network to interconnect multiple hosts
> docker network create --driver overlay --subnet [CIDR-range] [network-name]


**Ingress Network**
When a docker swarm is created, a load balancer is automatically created and it takes care of the ingress network and distributes load on worker node replicas. This applies to single-host and multiple-hosts architecture.

Under the hood, load balancers on every Docker hosts utilise a routing mesh. This is all done by the Docker swarm and there's no need for config setup.


**Embedded DNS**
Docker has a built-in DNS server(IP: 127.0.0.11) that resolves container names. Use container name instead of its IP as the container IP could change.



Reference:
https://docs.docker.com/network/