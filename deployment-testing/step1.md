The first step of our tutorial is to get everything ready, by setting up [Istio](https://istio.io/).

To do this we will start by downloading it.

`curl -L https://git.io/getLatestIstio | ISTIO_VERSION=1.0.0 sh -`{{execute T1}}

Following this, we can enter the folder and add the bin to our path.
`cd istio-1.0.0`{{execute T1}}

`export PATH=$PWD/bin:$PATH`{{execute T1}}

Now we need to set up the istio environment, by running the following commands:

`kubectl apply -f install/kubernetes/helm/istio/templates/crds.yaml -n istio-system`{{execute T1}}

`kubectl apply -f install/kubernetes/istio-demo-auth.yaml`{{execute T1}}

After the execution of the previous comands, we can check the status of the istio system pods.

`kubectl get pods -n istio-system`{{execute T1}}

Once all pods are either Running or Completed we can go to the next step (This might take some time).
