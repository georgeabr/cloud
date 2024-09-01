Some text  

First create the cluster in Azure Kubernetes, with the appropriate resource group and name.  

Run the below from the cloudshell to access the cluster:  
```
az aks get-credentials --resource-group myaksrg --name myakscluster
```

Run these to apply the deployment and service files:
```
kubectl apply -f nginx-deployment.yaml
kubectl apply -f nginx-service.yaml
```
You can check the status of your deployment and service using the following commands: 
```
kubectl get deployments
kubectl get services
```
To list pods and connect to a pod:
```
kubectl get pods
kubectl exec --stdin --tty nginx-deployment-7c79c4bf97-tjlqd -- /bin/bash
```
To return snapshot logs from all containers in pods defined by label `app=nginx`:
```
kubectl logs nginx-service --all-containers=true
```
