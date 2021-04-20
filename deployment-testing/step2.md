Now that istio is set up and running, we can continue by deploying our solution.

To do this we will return to the root folder and download the simple-web repository, which will contain all the necessary files for us to perform the rest of the tutorial.

`cd && git clone https://github.com/bubriks/simple-web`{{execute T1}}

Following the download, we can enter it.

`cd simple-web`{{execute T1}}

Once we have the simple website we need to tell Kubernetes to deploy it similar to what we did for Istio.
To deploy our solution on Kubernetes we will run the following script.
`kubectl apply -f deployment.yml`{{execute T1}}

The next command will allow our solution to work with istio.
`kubectl apply -f istio.yml`{{execute T1}}

Now again we must verify that everything is working by running the following command.
`kubectl get pods`{{execute T1}}

Wait for Kubernetes to finish and show status as "Running" for all pods, before continuing to the next step.
