docker container run -it --name sample alpine:3.21 /bin/sh

# apk update && apk add curl

# curl -I https:/google.com

# exit

docker container ls -a | grep sample

docker container diff sample

docker container commit sample my-alpine

docker image ls

docker image history my-alpine


docker image build -t pinger .

docker container run --rm -it pinger

docker container run --rm -it pinger -w 5 127.0.0.1

docker container run --rm -it --entrypoint ash pinger

# /bin/sh -c "wget -O - http://www.google.com"

