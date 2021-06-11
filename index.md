---
layout: default
---
![FAASJ Logo](https://habrastorage.org/webt/nj/ii/tr/njiitrvu9d27rb91dbzzw0iw7sy.png)

**FaaSJ makes it simple to deploy existing code to Kubernetes!**

Serverless is not about the physical absence of servers. It is a new approach to building systems in the cloud.
FaaSJ is a 100% pure Java serverless framework.

## Main features

*   Easy to deploy
*   Stateless
*   Scalable
*   Event-driven
*   Fast

## How to start
#### Setup a Kubernetes cluster
* Install k3d

* Start a cluster

* `k3d cluster create CLUSTER_NAME` to create a new single-node cluster.
`k3d kubeconfig merge CLUSTER_NAME --switch-context` to update your default kubeconfig

#### Deploy FaaSJ
Add the FaaSJ helm chart:
```
helm repo add faasj https://faasj.github.io/helm-chart/
```
Now deploy FaaSJ from the helm chart repo:

```
helm repo update && helm upgrade faasj --install faasj/faasj \
--namespace faasj  \
--set generateBasicAuth=true \
--set console=true
```
#### Log in
Log into your FaaSJ console:

```
kubectl port-forward svc/console -n faasj 8080:8080
```
Now you can deploy new functions!

