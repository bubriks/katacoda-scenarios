The first step of our tutorial is to get everything ready, by setting up [Istio](https://istio.io/).

Lets begin by starting the Kubernetes.

`launch.sh`{{execute T1}}

Next we can download the most recent istio (1.9.3 is most recent at the time of writting).

`curl -L https://istio.io/downloadIstio | ISTIO_VERSION=1.9.3 sh -`{{execute T1}}

Following this, we can add the bin folder of the downloaded istio to our path.

`export PATH=istio-1.9.3/bin:$PATH`{{execute T1}}

Now with we can instal istio.

`istioctl install --set profile=demo -y`{{execute T1}}

Lastly, lets instruct Istio to automatically inject Envoy sidecar proxies when deploying application.

`kubectl label namespace default istio-injection=enabled`{{execute T1}}

With this being done we can move on to the next step.