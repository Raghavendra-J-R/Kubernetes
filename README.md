**1. Create a Deployment named my-deployment1 using the nginx image**
```bash
 kubectl create deployment my-deployment1 --image=nginx
``` 
**kubectl**: The command-line tool for interacting with the Kubernetes API.

**create deployment**: Tells Kubernetes that you want to create a new Deployment. A Deployment is a Kubernetes object that manages a set of replicated Pods, ensuring that the specified number of replicas are running and updated.

**my-deployment1**: It is the name of the Deployment being created. In this case, the Deployment is named my-deployment1.

**--image=nginx**: It specifies the container image used for the Pods managed by this Deployment. The nginx image is a popular web server and reverse proxy server.

  It creates a Deployment named my-deployment1 that uses the nginx image. Deployments manage the rollout and scaling of applications.

**2. Expose the deployment as a service**
```
  kubectl expose deployment my-deployment1 --port=80 --type=NodePort --name=my-service1
```
It exposes the my-deployment1 Deployment as a Service named my-service1, making it accessible on port 80 through a NodePort. NodePort services allow external traffic to access the service.

**3. Lists all services in the default namespace. Services provide a stable IP address and DNS name for accessing a set of pods**
```
 kubectl get services
```
This command lists all the services in the default namespace, including nginx-service, and provides details such as the ClusterIP, NodePort, and target port.


**4. Get the list of pods**
```
kubectl get pods
```
This command displays all pods, including those created by the my-deployment1 Deployment.

**6. Show labels**
 ```
kubectl get pod <pod-name> --show-labels
```
This command will list the labels associated with the specified pod, helping you identify its attributes and categorization within your Kubernetes cluster.

**7. Label the pod**
```
kubectl label pods <pod-name> environment=deployment
```
The command is used in Kubernetes to label a specific pod with the key-value pair **environment=deployment** . This label helps categorize and manage pods based on their deployment environment, making it easier to organize and select Kubernetes objects within the cluster.


