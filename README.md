Tips:
- Use stretch-slim or alpine tag to save on space


Image building best practices:
- Create `.dockerignore` in the same folder as the Dockerfile
- Implement layer caching using `--no-cache`
- security scan images
> docker scan [image]
- view image layers
> sdocker image history --no-trunc [image]


**Visualizer**
https://hub.docker.com/r/dockersamples/visualizer

`docker pull dockersamples/visualizer`


**Practice Docker**
https://labs.play-with-docker.com/