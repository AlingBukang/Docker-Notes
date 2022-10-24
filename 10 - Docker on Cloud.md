**Docker Cloud**
- Docker's very own Orchestration-as-aservice platform; it doesn't host infrastructure
- To be used in conjuction with other Cloud infrastructure providers such as AWS, Azure, etc.



**AWS ECS**




**Kubernetes**
```sh
kubectl run --replicas=1000 [container]

# scale
kubectl scale --replicas=2000 [container]

# rolling update
kubectl scrolling-update [container] --image=web-server:2

# rollback
kubectl scrolling-update [container] --rollback
```