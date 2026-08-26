docker image build -t hello-world .

docker image ls | grep hello-world

docker image build -t hello-world-small \
-f Dockerfile.multi-step .

mkdir backup
docker image save -o ./backup/my-alpine.tar my-alpine

docker image load -i ./backup/my-alpine.tar

# Pushing images to a registry

docker image tag alpine:latest rajesh/alpine:1.0

docker login -u rajesh -p <my secret password>

docker image push gnschenker/alpine:1.0