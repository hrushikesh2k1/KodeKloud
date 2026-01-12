Create a Pod with name pod-nginx with nginx:latest image, namethe container as nginx-container and label the pod as app=nginx-app

Approach-1: Using yaml manifest
```
# pod.yaml
apiVersion: v1
kind: Pod
metadata:
  name: pod-nginx
  labels:
    app: nginx_app
spec:
  containers:
    - name: nginx-container
      image: nginx
```
```
kubectl apply -f pod.yaml
```

Approach-2: Using kubectl run cmd
```
kubectl run pod-nginx \
  --image=nginx \
  --overrides='
{
  "spec": {
    "containers": [
      {
        "name": "nginx-container",
        "image": "nginx"
      }
    ]
  }
}' \
  --labels=app=nginx_app
```
