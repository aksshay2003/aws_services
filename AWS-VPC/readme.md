# Amazon VPC Lab Setup

## Overview

This lab demonstrates the creation and configuration of a custom Amazon VPC with public and private subnets, along with secure access using a Bastion Host. The setup includes creating VPC, subnets, internet gateway, route tables, EC2 instances, and configuring SSH access between public and private instances.

## Components Created

- **VPC**

  - CIDR Block: `12.0.0.0/16`
  - Tagged for easy identification

- **Internet Gateway**

  - Created and attached to the VPC for internet access

- **Subnets**

  - **Public Subnet**
    - CIDR Block: `12.0.0.0/20`
    - Availability Zone: `us-east-1a`
  - **Private Subnet**
    - CIDR Block: `12.0.16.0/20`
    - Availability Zone: `us-east-1a`

- **Route Tables**

  - Public Route Table associated with the public subnet, routing `0.0.0.0/0` traffic to the Internet Gateway
  - Private Route Table associated with the private subnet, no direct internet access

- **EC2 Instances**
  - **Public Instance (Bastion Host)**
    - Located in public subnet
    - Public IP assigned
    - SSH enabled for external access
  - **Private Instance**
    - Located in private subnet
    - No public IP
    - SSH access only via Bastion Host

## Secure Access Workflow

1. Connect to the public EC2 instance (Bastion Host) via SSH using a private key.
2. From the Bastion Host, SSH into the private EC2 instance using its private IP and the securely copied private key.
3. This setup ensures private instances remain inaccessible directly from the internet, improving security.

## Purpose

This lab illustrates:

- How to design a secure VPC with isolated subnets.
- Configuring routing to allow internet access for public subnet resources.
- Using Bastion Hosts to securely manage access to private subnet instances.

---

_End of README_
