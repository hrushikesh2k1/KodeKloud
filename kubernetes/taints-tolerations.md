Prerequisite:
1. minikube installed

Goal:
1. How nodeSelector blocks scheduling
2. How taints block scheduling
3. How tolerations allow scheduling

## Observe the Node (labels and taints)
```
kubectl describe node minikube
```
<img width="824" height="535" alt="3" src="https://github.com/user-attachments/assets/fca63c90-37fd-4050-bb94-2c98f16acd4c" />

## nodeSelector WITHOUT matching label
```
kubectl run pod-selector --image=nginx --dry-run=client -o yaml > pod-selector.yaml
```
```
spec:
  nodeSelector:
    disktype: ssd
```
```
kubectl apply -f pod-selector.yaml
```
<img width="738" height="226" alt="1" src="https://github.com/user-attachments/assets/2b302c92-062e-4469-a5fe-06db0fbb2c06" />
<img width="839" height="581" alt="2" src="https://github.com/user-attachments/assets/589d4b00-f8a6-4e2b-8607-f6134dd06ea2" />

## Add the label to the NODE
```
kubectl label node minikube disktype=ssd
```
<img width="830" height="542" alt="4" src="https://github.com/user-attachments/assets/5546f5bf-541b-49df-858c-b958ffd0bcf9" />
```
kubectl get pods
```
<img width="803" height="149" alt="5" src="https://github.com/user-attachments/assets/65e43cd9-ecf4-4c77-9550-11747e23deb3" />

## Introduce TAINT
```
kubectl describe node minikube | grep Taints
```
```
kubectl taint node minikube dedicated=db:NoSchedule
```
```
kubectl describe node minikube | grep Taints
```
<img width="815" height="178" alt="6" src="https://github.com/user-attachments/assets/b3bad3c3-ff4b-4c30-861f-b917b571e033" />

## Create Pod WITHOUT toleration (should FAIL)
```
kubectl run pod-no-toleration --image=nginx
kubectl get pods
kubectl describe pod pod-no-toleration
```
<img width="793" height="185" alt="7" src="https://github.com/user-attachments/assets/0ab3312e-8f17-4d5f-bcd8-73ba73f13cf6" />
<img width="828" height="638" alt="8" src="https://github.com/user-attachments/assets/5389b018-72f1-40cf-acf5-487ac8fb0b45" />

## Add toleration (Permission granted)
```
kubectl run pod-with-toleration --image=nginx --dry-run=client -o yaml > pod-with-toleration.yaml
```
```
spec:
  tolerations:
  - key: "dedicated"
    operator: "Equal"
    value: "db"
    effect: "NoSchedule"
```
```
kubectl apply -f pod-with-toleration.yaml
kubectl get pods
```
<img width="779" height="250" alt="9" src="https://github.com/user-attachments/assets/e91d47dc-2102-47e8-b80b-65186bcb71b7" />

## cleanup
```
kubectl delete pod --all
kubectl taint node minikube dedicated=db:NoSchedule-
kubectl lable node minikube disktype-
```





