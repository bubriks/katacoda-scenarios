# Setup

this tutorial uses minicube

Get repository:

`git clone https://github.com/bubriks/simple-web`{{execute}}

Enter folder:

`cd simple-web`{{execute}}

# Intro to docker

Build docker container:

`docker build -t simple-web .`{{execute}}

Run the created docker container:

`docker run -d -p 80:80 simple-web`{{execute}}

Verify that container is running, by calling it and seeing that we receive html response.

`curl localhost:80`{{execute}}

Get all runing simple-web images, by executing the following script:

`docker ps --filter ancestor=simple-web`{{execute}}

Stop run by perfrming pause using the container id

`docker stop <container-id>`{{execute}} (replace container-id with id from previous step)

docker push bubriks/simple-web:green
# Setup Kubernetes

kubectl apply -f deployment.yml
minikube tunnel
minikube service simple-web

show and explain yml before running


install istio (needed for a/b testing as its bussines decision)








1
curl -L https://istio.io/downloadIstio | ISTIO_VERSION=1.9.2 sh -
cd istio-1.9.2
export PATH=$PWD/bin:$PATH

istioctl install
kubectl label namespace default istio-injection=enabled

git clone https://github.com/bubriks/simple-web
cd simple-web

kubectl apply -f deployment.yml
kubectl apply -f istio.yml