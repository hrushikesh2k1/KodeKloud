The Nautilus DevOps team is gearing up to deploy applications on a Kubernetes cluster for migration purposes. A team member has been tasked with creating a ReplicaSet outlined below:



Create a ReplicaSet using httpd image with latest tag (ensure to specify as httpd:latest) and name it httpd-replicaset.


Apply labels: app as httpd_app, type as front-end.


Name the container httpd-container. Ensure the replica count is 4.

Approach:
1. create a YAML file for replica set
```
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: httpd-replicaset
  labels:
    app: httpd_app
    type: front-end
spec:
  # modify replicas according to your case
  replicas: 4
  selector:
    matchLabels:
      type: front-end
      app: httpd_app
  template:
    metadata:
      labels:
        type: front-end
        app: httpd_app
    spec:
      containers:
      - name: httpd-container
        image: httpd:latest
```
2. Apply the configuration
   ```
   kubectl apply -f replica-set.yaml
   ```
3. Confirm the replia set
   ```
   kubectl get rs
   ```
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d7739881-fd2a-4603-9544-332e6b7adfe9" />
