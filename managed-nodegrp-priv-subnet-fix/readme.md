
# eksctl - cluster.yaml
# A cluster with a managed node group in private subnets
```
---
apiVersion: eksctl.io/v1alpha5
kind: ClusterConfig

metadata:
  name: managed-cluster
  region: us-west-2

managedNodeGroups:
  - name: managed-ng-1
    minSize: 2
    maxSize: 4
    desiredCapacity: 3
    volumeSize: 20
    tags:
      private-networking: true  // optional - creates in private subnet

  - name: managed-ng-2
    instanceType: t2.large
    minSize: 2
    maxSize: 3
    tags:
      private-networking: false // defaults to public subnet if not specified

```