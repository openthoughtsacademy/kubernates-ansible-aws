```
brew tap weaveworks/tap

brew install weaveworks/tap/eksctl

eksctl create cluster  --name  my_cluster --region ap-south-1 --nodegroup-name linux-nodes --node-type t2.micro --nodes 2

eksctl delete cluster my-cluster
```
