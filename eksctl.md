```
brew tap weaveworks/tap

brew install weaveworks/tap/eksctl

eksctl create cluster  --name  myawscluster --region ap-south-1 --nodegroup-name linux-nodes --node-type t2.micro --nodes 2  --node-ami-family Ubuntu2004 --ssh-access

eksctl delete cluster myawscluster
```
