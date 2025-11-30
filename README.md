# 🟦 **AWS Complete Guide — Zero to Hero**

*Designed for Cloud Engineers, DevOps Engineers, Trainers & Students*

---

## 📘 **1. Introduction to AWS**

AWS (Amazon Web Services) is the world’s most widely adopted cloud platform, offering 200+ services for compute, storage, networking, analytics, machine learning, DevOps, security, and serverless.

### 🔥 Key Benefits

* Pay-as-you-go billing
* Global infrastructure
* High availability & fault tolerance
* On-demand scalability
* Managed services reduce operational overhead

---

# 🟧 **2. AWS Global Infrastructure**

### 🌍 Components

* **Regions** → Physical locations across the globe
* **Availability Zones (AZs)** → Independent data centres within a region
* **Edge Locations** → Caches for CloudFront
* **Local Zones** → Low-latency zones

### 🗺️ Sample

`ap-south-1 (Mumbai)` = 3 AZs

---

# 🟩 **3. AWS Identity & Access Management (IAM)**

IAM is used for secure access control to AWS resources.

### 🔑 IAM Components

* **Users**
* **Groups**
* **Roles**
* **Policies (JSON)**

### 🛡️ Best Practices

* Use **MFA**
* Use **IAM Roles instead of IAM Users**
* Use **Least Privilege Access**
* Rotate access keys

### CLI Examples

```bash
aws iam list-users
aws iam create-user --user-name atul
aws iam attach-user-policy --user-name atul --policy-arn arn:aws:iam::aws:policy/AdministratorAccess
```

---

# 🟦 **4. Compute Services**

## 🖥️ EC2 (Elastic Compute Cloud)

Virtual servers in the cloud.

### Key Concepts

* AMI
* Instance Types (t2.micro, t3.medium…)
* Key Pair
* Security Groups
* Elastic IP

### EC2 Creation via CLI

```bash
aws ec2 run-instances \
--image-id ami-0abcdef1234567890 \
--instance-type t2.micro \
--key-name mykey \
--security-group-ids sg-12345 \
--subnet-id subnet-12345
```

---

## 🐳 EC2 + Docker Basic Setup

```bash
sudo yum update -y
sudo yum install docker -y
sudo systemctl start docker
sudo usermod -aG docker ec2-user
docker run hello-world
```

---

# 🟨 **5. Storage Services**

## 📦 S3 – Simple Storage Service

* Object storage
* Versioning
* Lifecycle Policies
* Static Website Hosting
* S3 Encryption (SSE-S3, SSE-KMS)

### S3 Bucket Creation

```bash
aws s3 mb s3://cloudnautic-demo-bucket
aws s3 cp file.txt s3://cloudnautic-demo-bucket
```

---

## 💽 EBS – Elastic Block Store

* Used with EC2
* SSD / HDD
* Snapshots
* Encryption

---

## 🗄️ EFS – Elastic File System

* Shared file system
* Highly available
* Mounts on multiple EC2s

---

# 🟧 **6. Networking Services**

## 🌐 VPC — Virtual Private Cloud

Private isolated network.

### Components

* VPC
* Subnets (Public / Private)
* Route Tables
* Internet Gateway
* NAT Gateway
* NACL
* Security Groups

### Create VPC via CLI

```bash
aws ec2 create-vpc --cidr-block 10.0.0.0/16
```

---

# 🟩 **7. Load Balancers & Auto Scaling**

## ⚖️ Load Balancers

* **ALB** → HTTP/HTTPS
* **NLB** → TCP/UDP
* **CLB** → Classic

## 🔄 Auto Scaling Group (ASG)

Automatically scale EC2 instances based on CPU / Network load.

---

# 🟪 **8. Databases**

## 🛢️ RDS

* MySQL, PostgreSQL, MariaDB, SQL Server, Oracle
* Multi-AZ
* Automated backups

## 🚀 DynamoDB

* NoSQL
* Serverless
* Pay-per-request

---

# 🟥 **9. Serverless Services**

## ⚡ AWS Lambda

Runs code without provisioning servers.

Example:

```python
def lambda_handler(event, context):
    return "Hello from Cloudnautic!"
```

## 🔄 EventBridge & API Gateway Integration

---

# 🟦 **10. Containers & Kubernetes**

## 🐳 ECS – Elastic Container Service

* Fargate (Serverless)
* EC2 Launch Type

## ☸️ EKS – Elastic Kubernetes Service

Basic cluster creation:

```bash
eksctl create cluster --name demo --region ap-south-1
```

---

# 🟧 **11. DevOps on AWS**

## 🔧 CI/CD Tools

* **CodeCommit**
* **CodeBuild**
* **CodeDeploy**
* **CodePipeline**
* GitHub + ECR + EKS Integration

## 🐳 Push Docker Image to ECR

```bash
aws ecr create-repository --repository-name demo
aws ecr get-login-password | docker login --username AWS --password-stdin <account>.dkr.ecr.<region>.amazonaws.com
docker build -t demo .
docker push <account>.dkr.ecr.<region>.amazonaws.com/demo
```

---

# 🟦 **12. Monitoring**

## 📊 CloudWatch

* Logs
* Metrics
* Alarms
* Dashboards

## 🔍 X-Ray

Tracing service

## ❤️ Prometheus + Grafana on EC2 / EKS (Your expertise!)

---

# 🛡️ **13. Security & Compliance**

* IAM
* KMS
* WAF
* Shield
* Secrets Manager
* GuardDuty

---

# 🟫 **14. Cost Optimization**

* AWS Budgets
* Cost Explorer
* Reserved Instances
* Spot Instances
* Compute Optimizer
* S3 Lifecycle Rules

---

# 🟪 **15. Hands-On Projects (Cloudnautic Recommended)**

### 🚀 Beginner

1. Host static website on S3
2. Launch EC2 with Apache/Nginx
3. VPC with public/private subnets

### 🔧 Intermediate

1. ALB + AutoScaling app
2. RDS-based web app
3. ECR + ECS Fargate deployment

### ☸️ Advanced

1. EKS Cluster with CI/CD
2. Serverless architecture with Lambda + API Gateway
3. Observability stack (Prometheus + Grafana)

---

# 🟦 **16. AWS Certification Path**

* Cloud Practitioner
* Solutions Architect Associate
* Developer Associate
* SysOps Associate
* DevOps Professional
* Solutions Architect Professional

---

# 🟩 **17. Useful Links**

* AWS Docs: [https://docs.aws.amazon.com](https://docs.aws.amazon.com)
* AWS CLI: [https://docs.aws.amazon.com/cli](https://docs.aws.amazon.com/cli)
* Well-Architected Framework

---
