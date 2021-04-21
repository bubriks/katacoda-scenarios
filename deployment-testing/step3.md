Since the idea of A/B testing is to provide business value, we need to find people who would be using the application. Luckily for the purposes of this tutorial, we can simulate this.

Running this command we will generate 5 requests every second for our solution.

```while true; do
  curl -s https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com
  echo -n .;
  sleep 0.2
done```{{execute T1}}

To monitor how these requests are handled we need more tools as neither Kubernetes nor Istio provides anything that we could use. However, Istio can utilize various addons which we can use for our purposes.

To begin with we need something that can record metrics of usage. For this, we will use Prometheus.

The installation is a straightforward process and for our pourposes, nothing more than single command needs to be run.

`kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.9/samples/addons/prometheus.yaml`{{execute T1}}

The visualization of metrics will be done using another open-source tool: Grafana. 

Here again, only single command needs to be executed.

`kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.9/samples/addons/grafana.yaml`{{execute T1}}

After setting up our monitoring solution we must expose it.

To begin with we need to change katacoda.yaml file by replacing the previous IP address with the current host IP.

`sed -i 's/172.17.0.54/[[HOST_IP]]/g' katacoda.yaml`{{execute T1}}

After the change, we can run it.

`kubectl apply -f katacoda.yaml`{{execute T1}}

No by using the following links we can experience the tools that we have installed.

Grafana.

https://[[HOST_SUBDOMAIN]]-3000-[[KATACODA_HOST]].environments.katacoda.com/dashboard/db/istio-mesh-dashboard

Prometheus.

https://[[HOST_SUBDOMAIN]]-9090-[[KATACODA_HOST]].environments.katacoda.com/

