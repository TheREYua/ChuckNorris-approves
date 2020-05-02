###create & deploy pods & service 

#####Step 1. Create a ConfigMap with the nginx configuration file. Incoming HTTP requests to port 80 will be forwarded to port 8090 on localhost.

>1. $ kubectl apply -f configMapNginxProxy.yaml  file 
>2. $ kubectl apply -f deployment file 
>3. $ kubectl apply -f service file 
>4. $ kubectl apply -f autoscaling.yaml

#####Step 2. Check ns is active

> $ kubectl get ns

1. deployment.extensions/ ... created 
2. service.extensions/... created 
3. verify that pods created & running
4. > $ kubectl get pods \

#####Step 3. Identify port on the node that is forwarded to the Pod: 
>$ kubectl describe service appli-ku 
NodePort:	<unset>	"someport like 31200/TCP"

#####Step 4. Now we can use your browser (or curl) to navigate to our node's port ^   to access the application through reverse proxy, as in:
http://host;
