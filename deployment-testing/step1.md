# istio

We are using newest istio version that was release just few days ago
Start kubernetes by lunching:
`launch.sh`{{execute T1}}
Once it is running we can 

`curl -L https://git.io/getLatestIstio | ISTIO_VERSION=1.0.0 sh -`{{execute T1}}

`cd istio-1.0.0`{{execute T1}}

`export PATH=$PWD/bin:$PATH`{{execute T1}}

`kubectl apply -f install/kubernetes/helm/istio/templates/crds.yaml -n istio-system`{{execute T1}}

`kubectl apply -f install/kubernetes/istio-demo-auth.yaml`{{execute T1}}

`kubectl get pods -n istio-system`{{execute T1}}

`cd`{{execute T1}}

`git clone https://github.com/bubriks/simple-web`{{execute T1}}

`cd simple-web`{{execute T1}}

`kubectl apply -f deployment.yml`{{execute T1}}

`kubectl apply -f istio.yml`{{execute T1}}

`kubectl get pods`{{execute T1}}

`ip route get 1 | awk '{print $NF;exit}'`{{execute T1}}

Insert the received ip in place of <received-ip> and run the command (this will replaced the previous string with new one, in this case our external cluster ip{not the same as localhost})
sed -i 's/172.17.0.54/<received-ip>/g' katacoda.yaml

After replacing ip we can run last yaml which would allow us to access the website with port 80 and dashboards

`kubectl apply -f katacoda.yaml`{{execute T1}}

```while true; do
  curl -s https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com > /dev/null
  echo -n .;
  sleep 0.2
done```{{execute T1}}

see site:
https://[[HOST_SUBDOMAIN]]-31380-[[KATACODA_HOST]].environments.katacoda.com/

Dashbord:
Grafana.
https://[[HOST_SUBDOMAIN]]-3000-[[KATACODA_HOST]].environments.katacoda.com/dashboard/db/istio-mesh-dashboard
Service Graph.
https://[[HOST_SUBDOMAIN]]-8088-[[KATACODA_HOST]].environments.katacoda.com/dotviz
Jaeger.
https://[[HOST_SUBDOMAIN]]-16686-[[KATACODA_HOST]].environments.katacoda.com/
Prometheus.
https://[[HOST_SUBDOMAIN]]-16686-[[KATACODA_HOST]].environments.katacoda.com/

---------------------------------------------------------------

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
-------------------------------------------------------------

`curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64`{{execute T1}}

`install minikube-linux-amd64 /usr/local/bin/minikube`{{execute T1}}

`sudo apt-get install -y conntrack`{{execute T1}}

`minikube start --driver=none`{{execute T1}}


`git clone https://github.com/bubriks/simple-web`{{execute T1}}

`cd simple-web`{{execute T1}}

`kubectl apply -f deployment.yml`{{execute T1}}


`cd`{{execute T1}}

`curl -L https://istio.io/downloadIstio | ISTIO_VERSION=1.9.3 sh -`{{execute T1}}

`cd istio-1.9.3`{{execute T1}}

`export PATH=$PWD/bin:$PATH`{{execute T1}}

`istioctl install`{{execute T1}}

`y`{{execute T1}}

`kubectl label namespace default istio-injection=enabled`{{execute T1}}


`cd`{{execute T1}}

`cd simple-web`{{execute T1}}

`kubectl apply -f istio.yml`{{execute T1}}

`istioctl analyze`{{execute T1}}


`export INGRESS_PORT=$(kubectl -n istio-system get service istio-ingressgateway -o jsonpath='{.spec.ports[?(@.name=="http2")].nodePort}')`{{execute T1}}

Terminal 2:
`minikube tunnel`{{execute T2}}


`echo $INGRESS_PORT`{{execute T1}}

Copy port number and enter it in the following site
https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com/.

`cd`{{execute T1}}

`cd istio-1.9.2`{{execute T1}}

`kubectl apply -f samples/addons`{{execute T1}}

`kubectl rollout status deployment/kiali -n istio-system`{{execute T1}}

`istioctl dashboard kiali`{{execute T1}}


curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube_latest_amd64.deb
sudo dpkg -i minikube_latest_amd64.deb
minikube start --driver=none

curl -L https://istio.io/downloadIstio | ISTIO_VERSION=1.9.2 sh -
cd istio-1.9.2
export PATH=$PWD/bin:$PATH
istioctl install
y
kubectl label namespace default istio-injection=enabled