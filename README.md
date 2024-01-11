# kind-multinode-K8s-cluster
kind multinode K8s cluster (https://www.youtube.com/watch?v=kkW7LNCsK74&t=129s)

Installing With A Package Manager
On macOS via Homebrew:
brew install kind
which kind

kind create cluster
- Default cluster context name is `kind`.

- ## three node (two workers) cluster config
Create a yaml file kind-config.yaml with the following configuration
```bash
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
- role: worker
- role: worker
```
This will create one control-plane and 2 worker nodes
```bash
kind create cluster --name mycluster --config kind-config.yaml
```
https://kind.sigs.k8s.io/docs/user/quick-start/

<img width="1377" alt="Screenshot 2024-01-11 at 13 18 27" src="https://github.com/frank-goa/kind-multinode-K8s-cluster/assets/137857643/fd6427bb-1971-4995-99b6-2d3d8af774df">

<img width="1378" alt="Screenshot 2024-01-11 at 13 20 18" src="https://github.com/frank-goa/kind-multinode-K8s-cluster/assets/137857643/a0c32165-6e67-4ef9-9f06-752501cdd58b">

<img width="1375" alt="Screenshot 2024-01-11 at 13 23 16" src="https://github.com/frank-goa/kind-multinode-K8s-cluster/assets/137857643/abef4c36-6fde-444a-92ca-02de19899964">

<img width="1401" alt="Screenshot 2024-01-11 at 13 31 37" src="https://github.com/frank-goa/kind-multinode-K8s-cluster/assets/137857643/664dd8d5-6384-4a12-9f9b-a05b09f8a58a">

<img width="1386" alt="Screenshot 2024-01-11 at 13 44 29" src="https://github.com/frank-goa/kind-multinode-K8s-cluster/assets/137857643/ae362df2-be5f-4e50-81f9-0a1d68d54bfb">

### Create a new cluster
<img width="1379" alt="Screenshot 2024-01-11 at 13 49 55" src="https://github.com/frank-goa/kind-multinode-K8s-cluster/assets/137857643/234caad1-de06-4c60-b960-1fe10d2a16fe">

### Create a new cluster named mycluster
<img width="1370" alt="Screenshot 2024-01-11 at 13 52 54" src="https://github.com/frank-goa/kind-multinode-K8s-cluster/assets/137857643/92b14258-483f-49fe-8b4e-1bbd27efaf10">
- it configures the kube-config file for both the clusters

### to interect with different clusers
<img width="1375" alt="Screenshot 2024-01-11 at 13 59 19" src="https://github.com/frank-goa/kind-multinode-K8s-cluster/assets/137857643/ba9bfe05-db62-425f-8179-0096eb08f961">

<img width="1379" alt="Screenshot 2024-01-11 at 14 07 17" src="https://github.com/frank-goa/kind-multinode-K8s-cluster/assets/137857643/1d281e16-3c81-4b3c-82f8-6d5f6acda400">

<img width="1377" alt="Screenshot 2024-01-11 at 14 10 10" src="https://github.com/frank-goa/kind-multinode-K8s-cluster/assets/137857643/597e71c7-04ce-4475-ac12-6a5914a105b5">

### Multimaster Cluster 
```bash
# a cluster with 3 control-plane nodes and 3 workers
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
- role: control-plane
- role: control-plane
- role: worker
```
<img width="1396" alt="Screenshot 2024-01-11 at 14 21 43" src="https://github.com/frank-goa/kind-multinode-K8s-cluster/assets/137857643/3cf30208-266f-4de1-afc0-9e2c59fb2cbd">

### We connect to the master through the loadbalancer
<img width="1396" alt="Screenshot 2024-01-11 at 14 25 19" src="https://github.com/frank-goa/kind-multinode-K8s-cluster/assets/137857643/04e2b5c7-9e99-482d-abcf-d4434cca03c7">


