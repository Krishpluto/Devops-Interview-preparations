# Kubernetes Scenario-based Interview Questions

## Scenario: Find Pod IP
**Task:** You have a pod named web-server running in the production namespace. You need to find out the IP address of this pod.
**Answer:** 
```bash
kubectl get pod web-server -n production -o=jsonpath='{.status.podIP}'
```

## Scenario: Scale Deployment
**Task:** You need to scale a deployment named nginx-deployment to 5 replicas.
**Answer:** 
```bash
kubectl scale deployment nginx-deployment --replicas=5
```

## Scenario: Expose Service
**Task:** You want to expose a service named nginx-service on port 80 using NodePort.
**Answer:** 
```bash
kubectl expose service nginx-service --type=NodePort --port=80
```

## Scenario: Troubleshoot Pending Pod
**Task:** A pod named database is stuck in Pending state. How do you troubleshoot it?
**Answer:** 
```bash
kubectl describe pod database
```

## Scenario: Update Deployment Image
**Task:** You need to update the image of a deployment named nginx-deployment to nginx:latest.
**Answer:** 
```bash
kubectl set image deployment/nginx-deployment nginx=nginx:latest
```

## Scenario: Delete Pod by Label
**Task:** You have a pod named nginx with the label app=web. You need to delete this pod.
**Answer:** 
```bash
kubectl delete pod -l app=web
```

## Scenario: View Container Logs
**Task:** You want to view the logs of a container named nginx in a pod named nginx-pod.
**Answer:** 
```bash
kubectl logs nginx-pod -c nginx
```

## Scenario: Check Rollout Status
**Task:** You have a deployment named app-deployment and you want to check the rollout status.
**Answer:** 
```bash
kubectl rollout status deployment/app-deployment
```

## Scenario: Create Namespace
**Task:** You want to create a namespace named development.
**Answer:** 
```bash
kubectl create namespace development
```

## Scenario: Execute Command in Container
**Task:** You need to execute a command inside a running container named nginx in a pod named nginx-pod.
**Answer:** 
```bash
kubectl exec -it nginx-pod -- /bin/bash
```

## Scenario: Create Persistent Volume
**Task:** You need to create a persistent volume named pv-data with 1Gi capacity.
**Answer:** 
```bash
kubectl apply -f - <<EOF
apiVersion: v1
kind: PersistentVolume
metadata:
 name: pv-data
spec:
 capacity:
 storage: 1Gi
 accessModes:
 - ReadWriteOnce
 persistentVolumeReclaimPolicy: Retain
 hostPath:
 path: /mnt/data
EOF
```

## Scenario: Schedule Pod on Specific Node
**Task:** You want to schedule a pod named nginx on a specific node named node1.
**Answer:** 
```bash
kubectl patch pod nginx -p '{"spec": {"nodeName": "node-1"}}'
```

## Scenario: Rollback Deployment
**Task:** You have a deployment named app-deployment and you want to rollback to the previous version.
**Answer:** 
```bash
kubectl rollout undo deployment/app-deployment
```

## Scenario: Create Secret
**Task:** You need to create a secret named db-secret with a username and password.
**Answer:** 
```bash
kubectl create secret generic db-secret --from-literal=username=myuser --from-literal=password=mypassword
```

## Scenario: List Pods with IP Addresses
**Task:** You want to list all the pods in the cluster along with their IP addresses.
**Answer:** 
```bash
kubectl get pods -o wide
```

## Scenario: Label Node
**Task:** You need to label a node named node-1 with environment=production.
**Answer:** 
```bash
kubectl label node node-1 environment=production
```

## Scenario: Create Deployment from YAML
**Task:** You want to create a deployment named nginx-deployment with 3 replicas using a YAML file.
**Answer (YAML File):**
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:latest
        ports:
        - containerPort: 80
```
**Apply YAML File:**
```bash
kubectl apply -f nginx-deployment.yaml
```

## Scenario: Add Label to Pod
**Task:** You need to add a label app=nginx to a pod named nginx-pod.
**Answer:** 
```bash
kubectl label pod nginx-pod app=nginx
```

## Scenario: Delete Service
**Task:** You have a service named nginx-service and you want to delete it.
**Answer:** 
```bash
kubectl delete service nginx-service
```

## Scenario: List Persistent Volumes
**Task:** You need to list all the persistent volumes in the cluster.
**Answer:** 
```bash
kubectl get pv
```

## Scenario: Check Resource Utilization
**Task:** You want to check the resource utilization of pods in the production namespace.
**Answer:** 
```bash
kubectl top pods -n production
```

## Scenario: Delete Pods in Namespace
**Task:** You need to delete all the pods in the development namespace.
**Answer:** 
```bash
kubectl delete pods --all -n development
```

## Scenario: View Pod YAML
**Task:** You want to view the YAML definition of a pod named nginx-pod.
**Answer:** 
```bash
kubectl get pod nginx-pod -o yaml
```

## Scenario: Create TCP Service
**Task:** You need to create a service named nginx-service to expose port 80 on TCP.
**Answer:** 
```bash
kubectl create service tcp nginx-service --tcp=80:80
```

## Scenario: Change Resource Requests
**Task:** You have a pod named nginx and you want to change its resource requests to 0.5 CPU and 512Mi memory.
**Answer:** 
```bash
kubectl set resources pod nginx --requests=cpu=0.5,memory=512Mi
```

## Scenario: Create Role
**Task:** You need to create a role named nginx-reader with read-only access to pods in the default namespace.
**Answer (YAML File):**
```yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  namespace: default
  name: nginx-reader
rules:
- apiGroups: [""]
  resources: ["pods"]
  verbs: ["get", "watch", "list"]
```
**Apply YAML File:**
```bash
kubectl apply -f nginx-reader-role.yaml
```

## Scenario: Check Node Status
**Task:** You want to check the status of all the nodes in the cluster.
**Answer:** 
```bash
kubectl get nodes
```

## Scenario: Check Kubernetes Version
**Task:** You need to check the version of Kubernetes server.
**Answer:** 
```bash
kubectl version
```

## Scenario: Check Event Details
**Task:** You

 want to check the details of a specific event in the cluster.
**Answer:** 
```bash
kubectl describe event <event-name>
```

## Scenario: Update Deployment Environment Variable
**Task:** You have a deployment named app-deployment and you want to update its environment variable DB_HOST to db-server.
**Answer:** 
```bash
kubectl set env deployment/app-deployment DB_HOST=db-server
```

## Scenario: Drain Node
**Task:** You want to drain a node named node-1 for maintenance.
**Answer:** 
```bash
kubectl drain node-1 --ignore-daemonsets
```

## Scenario: Expose Deployment as Service
**Task:** You have a deployment named app-deployment and you want to expose it as a service named app-service on port 8080.
**Answer:** 
```bash
kubectl expose deployment app-deployment --name=app-service --port=8080
```

## Scenario: Create Deployment with Labels
**Task:** You need to create a deployment named nginx-deployment with a specific label app=nginx.
**Answer (YAML File):**
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
 spec:
   containers:
   - name: nginx
     image: nginx:latest
     ports:
     - containerPort: 80
```
**Apply YAML File:**
```bash
kubectl apply -f nginx-deployment.yaml
```

## Scenario: View Previous Pod Logs
**Task:** You want to check the logs of the previous instance of a pod named nginx.
**Answer:** 
```bash
kubectl logs nginx –previous
```

## Scenario: Find External IP of Service
**Task:** You have a service named nginx-service and you want to find out its external IP.
**Answer:** 
```bash
kubectl get svc nginx-service -o=jsonpath='{.status.loadBalancer.ingress[0].ip}'
```

## Scenario: Expose Pod as Service
**Task:** You need to create a service named nginx-service to expose the nginx pods on port 8080.
**Answer:** 
```bash
kubectl expose pod nginx --name=nginx-service --port=8080
```

## Scenario: Annotate Deployment
**Task:** You have a deployment named app-deployment and you want to annotate it with description="App Deployment".
**Answer:** 
```bash
kubectl annotate deployment app-deployment description="App Deployment"
```

## Scenario: Create Role Binding
**Task:** You need to create a role binding named nginx-read-access to bind the nginx-reader role to a user named john.
**Answer (YAML File):**
```yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: RoleBinding
metadata:
  name: nginx-read-access
subjects:
- kind: User
  name: john
  apiGroup: rbac.authorization.k8s.io
roleRef:
  kind: Role
  name: nginx-reader
  apiGroup: rbac.authorization.k8s.io
```
**Apply YAML File:**
```bash
kubectl apply -f nginx-read-access.yaml
```

## Scenario: List Pods in Namespace
**Task:** You want to check the status of all the pods in the default namespace.
**Answer:** 
```bash
kubectl get pods -n default
```

## Scenario: Create Deployment in Namespace
**Task:** You need to create a deployment named nginx-deployment with a specific namespace production.
**Answer (YAML File):**
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  namespace: production
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
 spec:
   containers:
   - name: nginx
     image: nginx:latest
     ports:
     - containerPort: 80
```
**Apply YAML File:**
```bash
kubectl apply -f nginx-deployment.yaml
```

## Scenario: View Pod Logs Since Timestamp
**Task:** You want to view the logs of the container named nginx in a pod named nginx-pod since a specific timestamp.
**Answer:** 
```bash
kubectl logs nginx-pod -c nginx --since-time=<timestamp>
```

## Scenario: Update Service Port
**Task:** You have a service named nginx-service and you want to update it to use TCP port 8080.
**Answer:** 
```bash
kubectl edit svc nginx-service
```
Then change the port to 8080 in the opened editor.

## Scenario: Create Deployment with Resource Limits
**Task:** You need to create a deployment named nginx-deployment with specific resource limits: CPU=0.5 and memory=512Mi.
**Answer (YAML File):**
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
 spec:
   containers:
   - name: nginx
     image: nginx:latest
     resources:
       requests:
         cpu: 500m
         memory: 512Mi
```
**Apply YAML File:**
```bash
kubectl apply -f nginx-deployment.yaml
```

## Scenario: Delete Namespace Resources
**Task:** You have a namespace named development and you want to delete all the resources in it.
**Answer:** 
```bash
kubectl delete namespace development --grace-period=0 –force
```

## Scenario: Create Deployment with Specific Labels
**Task:** You need to create a deployment named nginx-deployment with specific labels env=prod and app=nginx.
**Answer (YAML File):**
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        env: prod
        app: nginx
 spec:
   containers:
   - name: nginx
     image: nginx:latest
     ports:
     - containerPort: 80
```
**Apply YAML File:**
```bash
kubectl apply -f nginx-deployment.yaml
```

## Scenario: View Node Details
**Task:** You want to view the details of a specific node named node-1.
**Answer:** 
```bash
kubectl describe node node-1
```

## Scenario: Create Service Account
**Task:** You need to create a service account named deployer in the default namespace.
**Answer:** 
```bash
kubectl create serviceaccount deployer
```

## Scenario: Check Pod Status in Namespace
**Task:** You want to check the status of a specific pod named nginx in the production namespace.
**Answer:** 
```bash
kubectl get pod nginx -n production
```

## Scenario: Check Rollout History
**Task:** You have a deployment named app-deployment and you want to check the rollout history.
**Answer:** 
```bash
kubectl rollout history deployment/app-deployment
```

## Scenario: Check

 Service Status
**Task:** You want to check the status of a specific service named nginx-service.
**Answer:** 
```bash
kubectl get service nginx-service
```