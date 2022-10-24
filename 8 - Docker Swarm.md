**Docker Swarm**
Elect leader node via quorum:
N / 2 + 1

```sh
# Run in Swarm manager
docker swarm init --advertise-addr [manager-ip]

# Request additional node manager
docker swarm join-token manager

# Request additional node worker
docker swarm join-token worker

# Promote a node worker to manager
# Run in master node
docker node promote [node-hostname]

# Display nodes
docker node ls

# To leave a cluster
docker swarm leave

# Delete a node
docker node rm [node-hostname]
```

**Create multiple instances of a container**
```sh
docker service create --replicas=[count] {-p 80:80} --name [name] {--network [network-name]} [container]

# Update replica count
docker service update --replicas=[count] [container-name/id]

# Run a global service, ex. install monitoring agent to all nodes
docker service create --mode global [container]

# Display running services
docker service ls

# Display running tasks
docker service ps

# Update a service, ex. add a port mapping
docker service update [container-name/id] --publish-add [host-port]:[container-port]

# Shutdown a node
docker node update --availability drain [node-name]

# Remove service
docker service rm [container-name]
```

**Connect multiple hosts**
```sh
# Implement an overlay network
docker network create --driver overlay --subnet [CIDR-range] [overlay-network-name]
# Create a service, ex. nginx, that can communicate with other services on connected hosts
docker service create --replicas [count] --network [overlay-network-name] [nginx]
```