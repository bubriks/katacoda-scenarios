Now with our solution running, we must make it and dashboards accessible. This is done by replacing the current value with the host ip address within the katacoda.yaml file.

`sed -i 's/172.17.0.54/[[HOST_IP]]/g' katacoda.yaml`{{execute T1}}

After the change, we can run the last yaml, which specifies how services can be accessed.

`kubectl apply -f katacoda.yaml`{{execute T1}}

We can view the site by clicking the following link below (might take some time to be available):

https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com/

If you see the same button color all the time don't forget about the browser cache. For most browsers, this can be solved by not using cache when developer tools are open. To do this press "Ctrl + Shift + I" and go to the Network section and check “Disable cache”. Another alternative is to use "Ctrl + f5" which is to refresh and ignore the cache.
