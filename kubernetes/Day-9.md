The Nautilus DevOps team is crafting jobs in the Kubernetes cluster. While they're developing actual scripts/commands, they're currently setting up templates and testing jobs with dummy commands. Please create a job template as per details given below:


Create a job named countdown-devops.

The spec template should be named countdown-devops (under metadata), and the container should be named container-countdown-devops

Utilize image debian with latest tag (ensure to specify as debian:latest), and set the restart policy to Never.

Execute the command sleep 5


Approach:
1. Create a yaml file called "job.yaml"
```
apiVersion: batch/v1
kind: Job
metadata:
  name: countdown-xfusion
spec:
  template:
    metadata:
      name: countdown-xfusion
    spec:
      containers:
        - name: container-countdown-xfusion
          image: debian:latest
          command:
            - sleep
            - "5"
      restartPolicy: Never
```
2. Apply the manifest
   ```
   kubectl apply -f job.yaml
   ```
3. Check the pod and job
   ```
   kubectl get all
   ```
   <img width="978" height="570" alt="image" src="https://github.com/user-attachments/assets/c0618c96-c7a7-43ff-80cc-7952d5b8777f" />

