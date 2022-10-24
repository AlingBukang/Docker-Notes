**Build complex Dockerfile using `docker-compose`**

Docker Compose is a tool that was developed to help define and share multi-container applications. 

*Version 3 supports Swarm and multi-network
*From version 2 to latest, no need to specify links

`docker-compose version`

Create config file in yml format:
> nano docker-compose.yml
```sh
version: '3'
services:
    redis:
        image: redis
        networks:
            - backend
    web:
        image: flask-webapp
        ports:
            - 5000:80
        networks:
            - backend
            - frontend    
    database:
        image: postgres:9.4
        environment:
            POSTGRES_PASSWORD: postgres
            POSTGRES_USER: postgres
        networks:
            - backend

networks:
    frontend:
    backend:
```

To run the stack:
```sh
docker-compose up
```


References:
https://docs.docker.com/compose/
https://docs.docker.com/engine/reference/commandline/compose/