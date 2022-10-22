Docker Swarm

`docker swarm init`

# create multiple instances of container app
`docker service create --replicas=[count] {-p 80:80} {--network [network-name]} [container]`


Kubernetes
`kubectl run --replicas=1000 [container]`
# scale
`kubectl scale --replicas=2000 [container]`
# rolling update
`kubectl scrolling-update [container] --image=web-server:2`