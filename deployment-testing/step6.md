We can continue by deploying our solution.

For this, we need to use the `simple-web` repository that we looked at before (during the CI/CD part of the tutorial).

`cd simple-web`{{execute T1}}

Once we have entered the simple-web folder we can deploy the solution on Kubernetes.

`kubectl apply -f deployment.yml`{{execute T1}}

The execution of this command will result in the creation of 2 deployments (each for a different version of the application) and a single service that we will be using.

To open our solution to the outside traffic and specify the routing rules (necessary for A/B testing) we need to create an Istio ingress gateway.
In this case, 50% of traffic will go to each version.

`kubectl apply -f istio.yml`{{execute T1}}

Now to verify that everything is working run the following command.

`kubectl get pods`{{execute T1}}

Wait for all pods to finish and show status as "Running", before continuing.

We can view the site by clicking the link below. It might take few seconds for the page to become available (If the issue persists check for advice below).

https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com/

Once you have noticed the different variations of the same website we can proceed to the Monitoring step (If only single button color is seen check for advice below).

# Issue: The provided link does not work
Verify that everything should be working, by checking that istio-ingressgateway has an external IP.

`kubectl get svc istio-ingressgateway -n istio-system`{{execute T1}}

In the unfortunate case of perpetually `<pending>` EXTERNAL-IP the Katacoda has failed to set up the load balancer.
But don't worry this issue can be circumvented by utilizing a node port when connecting to the cluster.
The following command will provide us with this port.

`export INGRESS_PORT=$(kubectl -n istio-system get service istio-ingressgateway -o jsonpath='{.spec.ports[?(@.name=="http2")].nodePort}') && echo $INGRESS_PORT`{{execute T1}}

Now we can use it in the previously provided link, by replacing port 80 with the received number.
After the change press `Display Port` to see the page.

# Issue: Single page variation
Don't forget about the cache, this could result in the browser displaying a single button color even after the page is refreshed/button clicked multiple times.
To solve this either:
- Use `Ctrl + f5` to refresh the page without using cache.
- Disable caching when developer tools are open. To do this press `Ctrl + Shift + I` and go to the Network section and check `Disable cache`.