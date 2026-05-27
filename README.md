# OluTech Solutions — 3-Tier AWS Architecture

![3-Tier AWS Architecture Diagram](OluTech%20Solutions-3-Tier%20AWS%20Architecture.drawio.png)

## Overview
...

## Overview
This architecture diagram documents a complete **3-tier AWS VPC networking stack** built hands-on during Week 3 of AWS Cloud Accelerator.

## Architecture Components

| Layer | Components |
|-------|------------|
| **Networking** | VPC (10.0.0.0/16), 2 Availability Zones, 6 Subnets (Public/Private App/Private DB) |
| **Internet Access** | Internet Gateway, NAT Gateway (AZ-A & AZ-B) |
| **Compute** | Application Load Balancer, EC2 App Servers (Multi-AZ) |
| **Database** | MySQL RDS (Multi-AZ) |

## CIDR Mapping

| Subnet | CIDR |
|--------|------|
| Public Subnet AZ-A | 10.0.1.0/24 |
| Private App Subnet AZ-A | 10.0.2.0/24 |
| Private DB Subnet AZ-A | 10.0.3.0/24 |
| Public Subnet AZ-B | 10.0.4.0/24 |
| Private App Subnet AZ-B | 10.0.5.0/24 |
| Private DB Subnet AZ-B | 10.0.6.0/24 |

## Security
- Security Groups control traffic between tiers:
  - SG-LB → SG-WebServers (Port 80/443)
  - SG-WebServers → SG-Database (Port 3306)

## What I Built Hands-On
- [x] VPC with custom CIDR
- [x] Public & Private subnets across 2 AZs
- [x] Internet Gateway + Route Tables
- [x] NAT Gateway for private subnet outbound access
- [x] Application Load Balancer
- [x] EC2 instances in private subnets
- [x] Multi-AZ RDS MySQL database

## Tools Used
- draw.io (diagrams.net)
- AWS Architecture Icons
