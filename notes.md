Run Minikube

minikube start --extra-config "apiserver.cors-allowed-origins=["http://boot.dev"]"

The extra configuration is just so we can hit your cluster from Boot.dev. You should see a message like "kubectl is now configured to use "minikube" cluster and "default" namespace by default".

Dashboard
minikube dashboard --port=63840

This will open a browser window with a locally hosted dashboard for your cluster. You can use this dashboard to view and manage your cluster. 

deploy a container to your local k8s cluster.
```
kubectl create deployment synergychat-web --image=docker.io/bootdotdev/synergychat-web:latest
```
make sure the deployment was successful, run:
kubectl get deployments

see a list of all your running pods.
kubectl get pods 
kubectl get pods -o wide

Print the logs
kubectl logs PODNAME

Kill 
kubectl delete pod PODNAME

Take a look at the YAML file 
kubectl get deployment synergychat-web -o yaml

Edit the deployment 
kubectl edit deployment synergychat-web

stable set of replica Pods running at any given time. 
kubectl get replicasets

download a copy of your deployment's YAML file and save it in your current directory:
kubectl get deployment synergychat-web -o yaml > web-deployment.yaml

To apply the changes, run:
kubectl apply -f web-deployment.yaml
kubectl apply -f web-service.yaml
(official) creating a YAML file and use
kubectl apply -f

minikube tunnel -c
<!-- synchat.internal to the web-service
synchatapi.internal to the api-service 
http://synchatapi.internal/healthz

-->

kubectl get pvc
kubectl get pv

// Namespace (ns)
kubectl get ns
kubectl create ns
kubectl create ns crawler

// ensure your resources are  redeployed in the crawler namespace:
kubectl -n crawler get pods
kubectl -n crawler get svc
kubectl -n crawler get configmaps

kubectl delete deployment <deployment-name>
kubectl delete service <service-name>
kubectl delete configmap <configmap-name>

# metrics with top:
kubectl top pod
# hpa will monitor the CPU usage of the pods in it's deployment
kubectl get hpa

kubectl apply -f 
kubectl delete deployment synergychat-