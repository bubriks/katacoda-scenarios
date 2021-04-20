Since the idea of A/B testing is testing with people, we need to find people to test with. Luckily you do not need to find people around you to do so, instead, we will simulate users using the website.

```while true; do
  curl -s https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com
  echo -n .;
  sleep 0.2
done```{{execute T1}}

The different dashboards that we have set up for monitoring can be found here:

Grafana.

To setup grafana dashboard execute the command:

`kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.9/samples/addons/grafana.yaml`{{execute T1}}


https://[[HOST_SUBDOMAIN]]-3000-[[KATACODA_HOST]].environments.katacoda.com/dashboard/db/istio-mesh-dashboard

Prometheus.

To setup prometheus dashboard execute the command:

`kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.9/samples/addons/prometheus.yaml`{{execute T1}}

https://[[HOST_SUBDOMAIN]]-9090-[[KATACODA_HOST]].environments.katacoda.com/

Now with our solution running, we must make it and dashboards accessible. This is done by replacing the current value with the host ip address within the katacoda.yaml file.

`sed -i 's/172.17.0.54/[[HOST_IP]]/g' katacoda.yaml`{{execute T1}}

After the change, we can run the last yaml, which specifies how services can be accessed.

`kubectl apply -f katacoda.yaml`{{execute T1}}

