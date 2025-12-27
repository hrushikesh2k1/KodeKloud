You are managing a Kubernetes cluster with multiple node pools:

Some nodes are GPU-enabled

Some nodes are spot/preemptible

Some nodes are high-memory

You have an application with these requirements:

Must run only on GPU nodes

Must avoid spot/preemptible nodes

Prefer nodes in zone us-east-1a, but should still run if not available


Approach:
I’d label GPU, spot, and zone information on nodes.
Then I’d use required node affinity to enforce GPU-only and non-spot scheduling, and preferred node affinity for zone preference.

Pod requirement:
1. Run only on GPU nodes.
2. Must Not run on spot/preemptible nodes.
3. Prefer zone us-east-1a, but don't fail if unavialble.

Kubernetes scheduling works only on labels.

Why Nodeselector is not enough?
1. Cannot exclude based on conditions.
2. cannot express preferences.

Labelling the nodes
```
kubectl label node node-1 node-type=gpu
kubectl label node node-1 lifecycle=on-demand
kubectl label node node-1 topology.kubernetes.io/zone=us-east-1a
```
```
kubectl label node node-2 node-type=gpu
kubectl label node node-2 lifecycle=on-demand
kubectl label node node-2 topology.kubernetes.io/zone=us-east-1b
```
```
kubectl label node node-3 node-type=gpu
kubectl label node node-3 lifecycle=spot
```
GPU vs non-GPU  [nodetype]
Spot vs on-demand  [lifecycle]
Zone   [standard topology label]


Pod manifest
```
apiVersion: v1
kind: Pod
metadata:
  name: gpu-app
spec:
  containers:
    - name: app
      image: nginx
  affinity:
    nodeAffinity:
      requiredDuringSchedulingIgnoredDuringExecution:
        nodeSelectorTerms:
          - matchExpressions:
              - key: node-type
                operator: In
                values:
                  - gpu
              - key: lifecycle
                operator: NotIn
                values:
                  - spot
      preferredDuringSchedulingIgnoredDuringExecution:
        - weight: 100
          preference:
            matchExpressions:
              - key: topology.kubernetes.io/zone
                operator: In
                values:
                  - us-east-1a

```
