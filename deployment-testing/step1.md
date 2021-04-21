The first step of our tutorial is to get everything ready, by setting up [Istio](https://istio.io/).

To begin with, let us make sure that the Kubernetes cluster is running.

`launch.sh`{{execute T1}}

Next, we can download the Istio version of our choice. For this tutorial, we are going to use the most recent at the time of writing.

`curl -L https://istio.io/downloadIstio | ISTIO_VERSION=1.9.3 sh -`{{execute T1}}

Following this, we can add the "istioctl" client to our path.

`export PATH=istio-1.9.3/bin:$PATH`{{execute T1}}

With this being done we can go on to the actual installation of the product. For this purpose we are using "demo" [configuration profile](https://istio.io/latest/docs/setup/additional-setup/config-profiles/). It is a good choice for starting as it offers a good set of defaults.

`istioctl install --set profile=demo -y`{{execute T1}}

Lastly, let's instruct Istio to automatically inject Envoy sidecar proxies when deploying the application.

`kubectl label namespace default istio-injection=enabled`{{execute T1}}

With this being done we can move on to the next step.