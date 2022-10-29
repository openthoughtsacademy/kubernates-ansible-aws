1. Create an EC2 Instance


3. Install AWSCLI

3. Install Kubectl

```
$ curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
$ chmod +x ./kubectl

$ sudo mv ./kubectl /usr/local/bin/kubectl

```
4. Create an IAM user with Route53, EC2, IAM and S3 full access
```
AmazonEC2FullAccess
AmazonRoute53FullAccess
AmazonS3FullAccess
IAMFullAccess
AmazonVPCFullAccess
```
5. aws configure
6.  Install Kops
```
$ curl -LO https://github.com/kubernetes/kops/releases/download/$(curl -s https://api.github.com/repos/kubernetes/kops/releases/latest | grep tag_name | cut -d '"' -f 4)/kops-linux-amd64

$ chmod +x kops-linux-amd64
$ sudo mv kops-linux-amd64 /usr/local/bin/kops
```
7. Create a Route53 private hosted zone
   Let name it bucket.cluster
   
8. Create S3 bucket
```
$ aws s3 mb s3://k8s.bucket.cluster
$ export KOPS_STATE_STORE=s3://k8s.bucket.cluster
```

8. Create SSH Keys
     ```
 $ ssh-keygen
     ```
9. Create Kubernetes Cluster Definitions on S3 bucket
```
$ kops create cluster --cloud=aws --zones=us-east-2b --name=demo.bucket.cluster --dns-zone=private-zone --dns private --state s3://demo.bucket.cluster

```
10. Create Cluster
```
$ kops update cluster k8s.bucket.cluster --state s3://k8s.bucket.cluster –yes
```

