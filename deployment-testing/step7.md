Since the idea of A/B testing is to provide business value, we need to be able to monitor it.
For this, we need more tools as neither Kubernetes nor Istio provides anything that we could use.
However, Istio can utilize various addons which will come useful.

To begin with we need something that can record metrics of usage. For this, we will use [Prometheus](https://prometheus.io).

The installation is a straightforward process and for our purposes, nothing more than single command needs to be run.

`kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.9/samples/addons/prometheus.yaml`{{execute T1}}

The visualization of metrics will be done using another open-source tool: [Grafana](https://grafana.com). 

Here again, only a single command needs to be executed.

`kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.9/samples/addons/grafana.yaml`{{execute T1}}

After setting up our monitoring solution we must expose it for it to be available.
But for that to work, we need to modify the provided `katacoda.yaml` file by replacing the previous IP address with the current host IP.

`sed -i 's/172.17.0.54/[[HOST_IP]]/g' katacoda.yaml`{{execute T1}}

After the change, we can apply the file.

`kubectl apply -f katacoda.yaml`{{execute T1}}

By using the following links we can experience the tools that we have installed.

Grafana.

https://[[HOST_SUBDOMAIN]]-3000-[[KATACODA_HOST]].environments.katacoda.com/dashboard/db/istio-mesh-dashboard

Prometheus.

https://[[HOST_SUBDOMAIN]]-9090-[[KATACODA_HOST]].environments.katacoda.com/

Now all that we need to do is to find people who would be willing to use the application, so we could see the changes in usage.
However, for now, we can simulate it using a command which will generate 5 requests every second.

```while true; do
  curl -s https://[[HOST_SUBDOMAIN]]-${INGRESS_PORT:-80}-[[KATACODA_HOST]].environments.katacoda.com
  echo -n .;
  sleep 0.2
done```{{execute T1}}
