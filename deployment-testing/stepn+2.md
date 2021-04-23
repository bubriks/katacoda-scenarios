Now that Istio is set up and running, we can continue by deploying our solution.

To do this we will download the simple-web repository, which will contain all the necessary files for us to perform the rest of the tutorial.

`git clone https://github.com/bubriks/simple-web`{{execute T1}}

Following the successful download, we can enter the folder that was created.

`cd simple-web`{{execute T1}}

Once we have entered the simple-web folder we can deploy the solution on Kubernetes. To do this the following script can be run.

`kubectl apply -f deployment.yml`{{execute T1}}

To open our solution to outside traffic and specify the routing rules (Necessary for A/B testing) we need to create an Istio ingress gateway.

`kubectl apply -f istio.yml`{{execute T1}}

Now we must verify that everything is working by running the following command.

`kubectl get pods`{{execute T1}}

Wait for all pods to finish and show status as "Running", before continuing.

We can view the site by clicking the following link below (might take some time to be available):

https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com/

Don't forget about the browser cache, this could result in displaying of single button color event after the page is refreshed/button clicked multiple times.
To solve this:
- Use "Ctrl + f5" to refresh the page without using cache
- Most browsers, can disable caching when developer tools are open. To do this press "Ctrl + Shift + I" and go to the Network section and check “Disable cache”.

Once you have noticed the different variations of the same website we can proceed to the next step.
