The Nautilus DevOps team is setting up recurring tasks on different schedules. Currently, they're developing scripts to be executed periodically. To kickstart the process, they're creating cron jobs in the Kubernetes cluster with placeholder commands. Follow the instructions below:



Create a cronjob named nautilus.


Set Its schedule to something like */7 * * * *. You can set any schedule for now.


Name the container cron-nautilus.


Utilize the nginx image with latest tag (specify as nginx:latest).


Execute the dummy command echo Welcome to xfusioncorp!.


Ensure the restart policy is OnFailure.


Approach:
1. Create the cronjob yaml
```bash
apiVersion: batch/v1
kind: CronJob
metadata:
  name: nautilus
spec:
  schedule: "*/7 * * * *"
  jobTemplate:
    spec:
      template:
        spec:
          restartPolicy: OnFailure
          containers:
            - name: cron-nautilus
              image: nginx:latest
              command:
                - /bin/sh
                - -c
                - echo Welcome to xfusioncorp!
```

2. Apply for the manifest
   ```bash
   kubectl apply -f cronjob.yaml
   ```
3. Check the logs
   ```bash
   kubectl logs <pod_logs>
   ```
 

<img width="1919" height="862" alt="image" src="https://github.com/user-attachments/assets/a78663f9-aec4-43b7-84cd-06f94795db40" />

   
