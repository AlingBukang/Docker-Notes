Docker has containerise running a local registry using the `registry:2` image.
By default, local registry store images in `/var/lib/registry/docker/registry/v2/repositories/` dir.


```sh
# Run the registry locally
docker run -dp 5000:5000 --restart always --name registry registry:2

# Check that 'registry:2' container is running
docker ps

# Pull source image - we will use the ubuntu image
docker pull ubuntu

# Check images in your local docker repo - should have the registry and ubuntu images
docker images

# Tag image
docker image tag ubuntu localhost:5000/ubuntu

# Check images in your local docker repo again - should have the registry,hello-world, and localhost:5000/ubuntu images
docker images

# Push image to local registry
docker push localhost:5000/ubuntu

# access the registry:2 container via shell and check pushed image
docker exec -it registry:2 /bin/sh
# hello-world should exists in this dir
ls -la /var/lib/registry/docker/registry/v2/repositories/

# Run the local image
docker run -it localhost:5000/ubuntu bash
```