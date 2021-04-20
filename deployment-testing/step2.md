Now that istio is set up and running, we can continue by deploying our solution.

To do this we will download the simple-web repository, which will contain all the necessary files for us to perform the rest of the tutorial.

`git clone https://github.com/bubriks/simple-web`{{execute T1}}

Following the download, we can enter it.

`cd simple-web`{{execute T1}}

Once we have the simple website we need to tell Kubernetes to deploy it similar to what we did for Istio.
To deploy our solution on Kubernetes we will run the following script.

`kubectl apply -f deployment.yml`{{execute T1}}

The next command will allow our solution to work with istio.

`kubectl apply -f istio.yml`{{execute T1}}

Now again we must verify that everything is working by running the following command.

`kubectl get pods`{{execute T1}}

Wait for pods to finish and show status as "Running" for all pods, before continuing.

We can view the site by clicking the following link below (might take some time to be available):

https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com/

If you see the same button color all the time don't forget about the browser cache. For most browsers, this can be solved by not using cache when developer tools are open. To do this press "Ctrl + Shift + I" and go to the Network section and check “Disable cache”. Another alternative is to use "Ctrl + f5" which is to refresh and ignore the cache.
