This is a repository of my personal notes on using Docker, a platform that allows you to build, run, and share applications using containers. Docker can help you create a consistent and portable development environment, as well as simplify the deployment process of your applications.

I hope you find this repository helpful and informative.

Keep learning!



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
