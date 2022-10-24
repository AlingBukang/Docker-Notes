**Docker Stack**
A stack can contain multiple services which can compose of multiple containers.
Ex. A stack has a service running called nginx that runs on multiple container replicas for high availability.

```sh
docker stack deploy [container] --compose-file [compose-filename.yml]
```

Sample Stack Definition - replica
- Docker swarm will place containers to random nodes
  
> nano docker-compose.yml
```sh
version: 3
services:
    redis:
        image: redis
        deploy:
            replicas: 1
    db:
        image: postgres:9.4
        deploy:
            replicas: 2
    my-app:
        image: my-app
        deploy:
            replicas: 2        
```

Sample Stack Definition - placement
- Docker swarm will place containers to specified nodes
  
> nano docker-compose.yml
```sh
version: 3
services:
    redis:
        image: redis
        deploy:
            placement:
                constraints:
                    - node.hostname == [node-name]
    db:
        image: postgres:9.4
        deploy:
            replicas: 2
    my-app:
        image: my-app
        deploy:
            replicas: 2        
```


Sample Stack Definition - resources
- Docker swarm will specify limits on resources
  
> nano docker-compose.yml
```sh
version: 3
services:
    redis:
        image: redis
        deploy:
            replicas:1
            resources:
                limits:
                    cpus: 0.01
                    memory: 50M
    db:
        image: postgres:9.4
        deploy:
            replicas: 2
    my-app:
        image: my-app
        ports:
            80:80
        deploy:
            replicas: 2        
```

