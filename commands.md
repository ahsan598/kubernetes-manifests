### Cluster & Resource Commands
- **Get Cluster Info:** `kubectl cluster-info`
- **Detailed cluster debug info:** `kubectl cluster-info dump`
- **List available contexts:** `kubectl config get-contexts`
- **List all API resources:** `kubectl api-resources`
- **Explain any resource field:** `kubectl explain <resource-name>` (`kubectl explain deployment.spec`)

### Basic Commands:
- **Get all objects in kube-system:** `kubectl get all -n kube-system`
- **Get all objects in all namespaces:** `kubectl get -A`
- **Get Nodes:** `kubectl get nodes -o wide`
- **Get Pods:** `kubectl get pods -o wide`
- **Get Services:** `kubectl get services  -o wide`
- **Get Deployments:** `kubectl get deployments  -o wide`

### Creating Resources:
- **Create a Pod:** `kubectl run nginx --image=nginx`
- **Create a Deployment:** `kubectl create deployment nginx --image=nginx`
- **Create a Service:** `kubectl expose deployment nginx --port=80 --target-port=80`
- **Apply Configuration from File:** `kubectl apply -f <filename>.yaml`

### Manifest Generation (Dry Run)
- **Create deployment YAML without creating resource:** `kubectl create deploy <deploy-name> --image=<image-name> --dry-run=client -o yaml > deploy.yaml`
- Validate YAML before applying: `kubectl apply --dry-run=client -f <filename>.yaml`

### Viewing and Describing Resources:
- **Describe a Node:** `kubectl describe node <node-name>`
- **Describe a Pod:** `kubectl describe pod <pod-name>`
- **Describe a Service:** `kubectl describe service <service-name>`

### Editing & Deleting Resources:
- **Edit a Deployment:** `kubectl edit deployment <deployment-name>`
- **Delete a Pod:** `kubectl delete pod <pod-name>`
- **Delete a Deployment:** `kubectl delete deployment <deployment-name>`
- **Delete a Service:** `kubectl delete service <service-name>`

### Logs and Debugging:
- **Get Pod Logs:** `kubectl logs -f <pod-name>`
- **Get Logs for a Specific Container in a Pod:** `kubectl logs <pod-name> -c <container-name>`
- **Execute Command in Pod:** `kubectl exec -it <pod-name> -- /bin/bash`
- **Port Forwarding:** `kubectl port-forward <svc-name> <local-port>:<pod-port>`
- **Check DNS inside pod:** `kubectl exec -it <pod> -- cat /etc/resolv.conf`

### Scaling & Namespace Management:
- **Scale a Deployment:** `kubectl scale deployment <deployment-name> --replicas=<number-of-replicas>`
- **Create a Namespace:** `kubectl create namespace <namespace-name>`
- **Get Namespaces:** `kubectl get namespaces`
- **Use a Namespace:** `kubectl config set-context --current --namespace=<namespace-name>`

### Configuration Management:
- **Create ConfigMap:** `kubectl create configmap <configmap-name> --from-literal=<key>=<value>`
- **Create Secret:** `kubectl create secret generic <secret-name> --from-literal=<key>=<value>`
