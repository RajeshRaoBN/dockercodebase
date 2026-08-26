docker version

docker container run alpine echo "Hello World"

docker container run quay.io/centos/centos echo "Hello World on centos"

brew install jq

docker container run --detach --name trivia fundamentalsofdocker/trivia:ed4

docker container ls -l

docker rm --force trivia

docker container run alpine echo "Hello World"
docker container run --detach quay.io/centos/centos:stream9 sleep 3600

docker container ls -l

docker container ls --all

docker container ls --quiet

docker container rm --force $(docker container ls --all --quiet)

docker container ls --help

docker container run -d --name trivia fundamentalsofdocker/trivia:ed4

docker container stop trivia

export CONTAINER_ID=$(docker container ls -a | grep trivia | awk '{print $1}')
echo $CONTAINER_ID

docker container stop $CONTAINER_ID

docker container start $CONTAINER_ID

docker container start trivia

docker container rm <container name>

docker container rm <container ID>

docker container rm <container ID> --force

docker container rm -f trivia

docker container run -d --name trivia fundamentalsofdocker/trivia:ed4

docker container inspect trivia

docker container inspect -f "{{json .State}}" trivia | jq .

docker container exec -i -t trivia /bin/sh

/app # ps

docker container exec trivia ps

docker container exec -it -e MY_VAR="Hello World" trivia /bin/sh

/app # echo $MY_VAR

/app # <CTRL-d>

docker container rm -f trivia

docker container run -d --name trivia fundamentalsofdocker/trivia:ed4

docker container attach trivia

docker container rm --force trivia

docker run -d --name nginx -p 8080:80 nginx:alpine

curl -4 localhost:8080

docker container attach nginx
for n in {1..10} do; curl -4 localhost:8080 done;

docker container rm nginx

docker container run -d --name trivia fundamentalsofdocker/trivia:ed4

docker container logs trivia

docker container logs --tail 5 trivia

docker container logs --tail 5 --follow trivia

docker container rm --force trivia

docker container run --name test -it \
--log-driver none \
busybox sh -c \
'for N in 1 2 3; do echo "Hello $N"; done'

docker container logs test

docker container rm test