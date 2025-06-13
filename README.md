# NAT Gateway VPC Project

This project demonstrates how to set up a Virtual Private Cloud (VPC) on AWS with a NAT Gateway to enable secure internet access for private EC2 instances.

## Features
- Custom VPC with public and private subnets
- NAT Gateway for internet access from private subnet
- Internet Gateway for public subnet
- Route tables and associations
- EC2 instances in public and private subnets
- Apache web server installed on private instance
- SSH access via public instance (bastion host)

## Tools & Technologies
- AWS Management Console
- Terraform (Infrastructure as Code)
- Apache Web Server
- SSH Terminal (Command Line)

## Project Structure
```
natgateway-vpc-project/
├── main.tf
├── README.md
├── setup_instructions.md
└── screenshots/
    └── [your 13 images]
```

## How to Use
1. Clone this repository
2. Replace placeholder values in `main.tf` with your AWS settings
3. Run `terraform init && terraform apply`
4. Follow `setup_instructions.md` for verification steps

## License
This project is open-source and available under the MIT License.
