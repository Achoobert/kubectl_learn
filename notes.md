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

kubectl get pvc
kubectl get pv