docker container run rancher/cowsay hello

minikube start

kubectl config get-contexts

kubectl apply -f nginx.yaml

kubectl get pods

kubectl get services

minikube service nginx-service

kubectl port-forward svc/nginx-service 8080:80

kubectl expose pod nginx-deployment --type=NodePort --port=80

kubectl delete service nginx

kubectl delete pod nginx

minikube stop

minikube start --nodes 3 p demo

kubectl get nodes

minikube stop -p demo

minikube delete --all





kind version

kind create cluster

kind get clusters

kind create cluster --name demo

kind get clusters

kind delete clusters --all




minikube start -p minikube-demo
kind create cluster --name kind-demo

kubectl config get-contexts

kubectl config get-contexts minikube-demo

kubectl get nodes

kubectl apply -f nginx.yaml

kubectl port-forward nginx 8080:80

kubectl delete -f nginx.yaml

minikube delete --all
kind delete cluster --name kind-demo