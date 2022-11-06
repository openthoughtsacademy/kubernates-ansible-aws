```
brew tap weaveworks/tap

brew install weaveworks/tap/eksctl

eksctl create cluster  --name  myawscluster --region ap-south-1 --nodegroup-name linux-nodes --node-type t2.micro --nodes 2 --node-ami ami-062df10d14676e201 --ssh-access

eksctl delete cluster myawscluster
```
