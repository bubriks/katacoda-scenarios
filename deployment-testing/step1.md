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








---------------------------------------------------------------
`git clone https://github.com/bubriks/simple-web`{{execute}}

`cd simple-web`{{execute}}

`kubectl apply -f deployment.yml`{{execute}}


`cd`{{execute}}

`curl -L https://istio.io/downloadIstio | ISTIO_VERSION=1.9.2 sh -`{{execute}}

`cd istio-1.9.2`{{execute}}

`export PATH=$PWD/bin:$PATH`{{execute}}

`istioctl install`{{execute}}

`kubectl label namespace default istio-injection=enabled`{{execute}}


`cd`{{execute}}

`cd simple-web`{{execute}}

`kubectl apply -f istio.yml`{{execute}}

`istioctl analyze`{{execute}}


`export INGRESS_PORT=$(kubectl -n istio-system get service istio-ingressgateway -o jsonpath='{.spec.ports[?(@.name=="http2")].nodePort}')`{{execute}}

`export SECURE_INGRESS_PORT=$(kubectl -n istio-system get service istio-ingressgateway -o jsonpath='{.spec.ports[?(@.name=="https")].nodePort}')`{{execute}}

`export INGRESS_HOST=$(minikube ip)`{{execute}}

`export GATEWAY_URL=$INGRESS_HOST:$INGRESS_PORT`{{execute}}

Terminal 2:
`minikube tunnel`{{execute}}


`echo $INGRESS_PORT`{{execute}}

`curl http://$GATEWAY_URL`{{execute}}


`kubectl apply -f samples/addons`{{execute}}

`kubectl rollout status deployment/kiali -n istio-system`{{execute}}

`istioctl dashboard kiali`{{execute}}