`curl -L https://git.io/getLatestIstio | ISTIO_VERSION=1.0.0 sh -`{{execute T1}}

`cd istio-1.0.0`{{execute T1}}

`export PATH=$PWD/bin:$PATH`{{execute T1}}

`kubectl apply -f install/kubernetes/helm/istio/templates/crds.yaml -n istio-system`{{execute T1}}

`kubectl apply -f install/kubernetes/istio-demo-auth.yaml`{{execute T1}}

`kubectl get pods -n istio-system`{{execute T1}}

Wait until status of all is Running or Completed. (use previous command to verify)

`cd`{{execute T1}}

`git clone https://github.com/bubriks/simple-web`{{execute T1}}

`cd simple-web`{{execute T1}}

`kubectl apply -f deployment.yml`{{execute T1}}

`kubectl apply -f istio.yml`{{execute T1}}

`kubectl get pods`{{execute T1}}

Wait until status of all is Running. (use previous command to verify)

`sed -i 's/172.17.0.54/[[HOST_IP]]/g' katacoda.yaml`{{execute T1}}

After replacing ip we can run last yaml which would allow us to access the website with port 80 and dashboards

`kubectl apply -f katacoda.yaml`{{execute T1}}

Use next script to imitate service being used.

```while true; do
  curl -s https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com > /dev/null
  echo -n .;
  sleep 0.2
done```{{execute T1}}

see site by clicking the following link (might take some time to be available):

https://[[HOST_SUBDOMAIN]]-31380-[[KATACODA_HOST]].environments.katacoda.com/

if you see same button color all the time dont forget about cache (for most browsers this can be solved by not using cache when develper tools are open. to do this press "Ctrl + Shift + I" go to network section and check “Disable cache”)


Dashbord:

Grafana.

https://[[HOST_SUBDOMAIN]]-3000-[[KATACODA_HOST]].environments.katacoda.com/dashboard/db/istio-mesh-dashboard

Service Graph.

https://[[HOST_SUBDOMAIN]]-8088-[[KATACODA_HOST]].environments.katacoda.com/dotviz

Jaeger.

https://[[HOST_SUBDOMAIN]]-16686-[[KATACODA_HOST]].environments.katacoda.com/

Prometheus.

https://[[HOST_SUBDOMAIN]]-9090-[[KATACODA_HOST]].environments.katacoda.com/
