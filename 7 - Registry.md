Image Registry Providers:
- AWS
- Azure
- GCP
- DockerHub
- Local private registry

Login with DockerID to push and pull images from Docker Hub
`docker login [registry-server]`

image: [user]/[image-name]


# Deploy image to privately hosted registry
`docker run -dp 5000:5000 --name registry registry:2`
# pull source image
`docker pull [source-image]`
# tag image
`docker image tag [source-image] localhost:5000/[target-image]`
# push image
`docker push localhost:5000/[target-image]`

# check the list of images pushed
`curl -X GET localhost:5000/v2/_catalog`