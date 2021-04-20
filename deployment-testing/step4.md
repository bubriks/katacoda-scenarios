Since the idea of A/B testing is testing with people, we need to find people to test with. Luckily you do not need to find people around you to do so, instead, we will simulate users using the website.

```while true; do
  curl -s https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com > /dev/null
  echo -n .;
  sleep 0.2
done```{{execute T1}}

The different dashboards that we have set up for monitoring can be found here:

Grafana.

https://[[HOST_SUBDOMAIN]]-3000-[[KATACODA_HOST]].environments.katacoda.com/dashboard/db/istio-mesh-dashboard

Service Graph.

https://[[HOST_SUBDOMAIN]]-8088-[[KATACODA_HOST]].environments.katacoda.com/dotviz

Jaeger.

https://[[HOST_SUBDOMAIN]]-16686-[[KATACODA_HOST]].environments.katacoda.com/

Prometheus.

https://[[HOST_SUBDOMAIN]]-9090-[[KATACODA_HOST]].environments.katacoda.com/
