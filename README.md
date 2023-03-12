### Kubernetes, AWS EKS, AWS Fargate manually

### Technologies Used:

Kubernetes, AWS EKS, Nginx, AWS Fargate

### Project Description:

1- Configure necessary IAM Roles

2- Create VPC with Cloudformation Template for Worker Nodes

3- Create EKS cluster (Control Plane Nodes)

4- Create Fargate IAM Role

5- Create Fargate Profile

6- Deploy an example application to EKS cluster using Fargate profile

### Instructions:

###### Step 1: Create AWS IAM role for EKS cluster

![image](/images/Screenshot%202023-03-12%20at%208.03.22%20pm.png)

###### Step 2: Create customized VPC for K8s Worker nodes by AWS cloudformation

![image](/images/Screenshot%202023-03-12%20at%208.08.34%20pm.png)

###### Step 3: Create EKS cluster and connect it to created VPC

![image](/images/Screenshot%202023-03-12%20at%201.09.20%20pm.png)
![image](/images/Screenshot%202023-03-12%20at%201.11.58%20pm.png)

###### Step 4: Configure kubectl to AWS EKS cluster

```
aws configure list
```

```
aws eks update-kubeconfig --name eks-cluster-nginx
```

```
kubectl get ns
```

```
kubectl cluster-info
```

###### Step 5: Create a role for Fargate

![image](/images/Screenshot%202023-03-12%20at%209.55.56%20pm.png)

###### Step 6: Create Fargate to eks cluster and attach the role to Fargate

![image](/images/Screenshot%202023-03-12%20at%2010.08.32%20pm.png)

###### Step 7: Remove public subnet in Fargate profile

###### Step 8: add namespace and label in nginx.file and add info to fargate profile

![image](/images/Screenshot%202023-03-12%20at%2010.11.45%20pm.png)
![image](/images/Screenshot%202023-03-12%20at%2010.11.55%20pm.png)
![image](/images/Screenshot%202023-03-12%20at%2010.13.49%20pm.png)
![image](/images/Screenshot%202023-03-12%20at%2010.14.07%20pm.png)

###### Step 9: Create a namespace: dev by kubectl

```
kubectl crate ns dev
```

###### Step 10:deploy a nginx app into eks cluster

```
kubectl apply -f nginx-dev.yaml
```
