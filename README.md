# Scalable Web Application using AWS NLB and Auto Scaling with Python & Boto3

## 📌 Project Overview

This project demonstrates how to automate the deployment of a scalable and highly available web application using Python and Boto3 with AWS Network Load Balancer (NLB), Auto Scaling Group, and Amazon EC2.

The infrastructure was created programmatically using Python scripts and the Boto3 AWS SDK instead of manual AWS Console configuration.

The Network Load Balancer distributes incoming traffic across multiple EC2 instances, while Auto Scaling automatically launches or terminates instances based on traffic demand.

---

## 🧰 AWS Services Used

- Amazon EC2
- Network Load Balancer (NLB)
- Auto Scaling Group (ASG)
- Target Groups
- Python
- Boto3

---

## 🎯 Project Objectives

- Automate AWS infrastructure creation using Python
- Deploy scalable EC2 instances
- Configure Network Load Balancer
- Implement Auto Scaling
- Handle high-performance and low-latency traffic

---

## 🚀 Implementation Steps

### 1. Create EC2 Instances using Boto3

Used Python and Boto3 to launch EC2 instances automatically.

Configured:
- Amazon Linux AMI
- Security Groups
- HTTP and SSH access

---

### 2. Configure Web Server

Installed Apache Web Server on EC2 instances.

```bash
sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
```

Created test web page:

```bash
echo "Hello from $(hostname)" | sudo tee /var/www/html/index.html
```

---

### 3. Create Target Group

Created a target group for registering EC2 instances.

Configuration:
- Protocol: TCP
- Port: 80
- Health Checks Enabled

---

### 4. Create Network Load Balancer

Configured an Internet-facing Network Load Balancer.

Features:
- High Performance
- Low Latency
- TCP Traffic Handling

The NLB distributes traffic across healthy EC2 instances.

---

### 5. Create Launch Template

Automated launch template creation using Boto3.

Included:
- AMI ID
- Instance Type
- Security Group
- User Data Script

---

### 6. Create Auto Scaling Group

Configured Auto Scaling Group with:
- Desired Capacity: 2
- Minimum Capacity: 1
- Maximum Capacity: 4

Attached the Auto Scaling Group to the NLB target group.

---

### 7. Test Load Balancing

Accessed the NLB DNS endpoint to verify traffic distribution between multiple EC2 instances.

---

## 🎯 Features

- Infrastructure Automation using Python and Boto3
- High Performance Load Balancing
- Auto Scaling
- Fault Tolerance
- Scalable Architecture

---

## 📸 Output

The Network Load Balancer successfully distributed incoming traffic across multiple EC2 instances, while Auto Scaling automatically managed server capacity.

---

## 🎓 Learning Outcomes

- AWS automation using Boto3
- EC2 provisioning using Python
- NLB configuration
- Auto Scaling implementation
- Infrastructure as Code concepts

---

## ✅ Conclusion

This project successfully automated the deployment of a scalable and highly available AWS infrastructure using Python, Boto3, Network Load Balancer, and Auto Scaling Group to efficiently handle high-performance traffic workloads.
