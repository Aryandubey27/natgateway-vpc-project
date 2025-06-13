# Setup Instructions for NAT Gateway VPC Project

## Step-by-Step Guide

### 1. Create a VPC
- CIDR: `10.0.0.0/16`

### 2. Create Two Subnets
- Public Subnet: `10.0.1.0/24`
- Private Subnet: `10.0.2.0/24`

### 3. Add an Internet Gateway
- Attach it to your VPC

### 4. Create a NAT Gateway
- Allocate an Elastic IP
- Launch NAT Gateway in the **public subnet**

### 5. Create Route Tables
- Public Route Table:
  - Route `0.0.0.0/0` → Internet Gateway
- Private Route Table:
  - Route `0.0.0.0/0` → NAT Gateway
- Associate subnets with respective route tables

### 6. Launch EC2 Instances
- **Bastion Host** in public subnet (with public IP)
- **Web Server** in private subnet (no public IP)

### 7. Connect and Install Apache
- SSH into bastion host
- From there, SSH into the private EC2 instance
- Run:
  ```bash
  sudo apt update -y
  sudo apt install apache2 -y
  sudo systemctl start apache2
  ```

### 8. Verify Apache Server
- Use curl or browser from bastion host to access `http://<private-ip>`

### 9. Refer to Screenshots
See `screenshots/` folder for visual steps, named in sequence by timestamp.

---
Ensure your security groups allow:
- SSH (port 22) for bastion host
- HTTP (port 80) for web server from within the VPC
