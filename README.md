## Project Overview

In this project I built a secure multi-tier network architecture using Amazon 
VPC, creating a private subnet that completely isolates backend resources from 
the public internet using dedicated route tables and custom Network ACLs.

## AWS Services Used
- Amazon VPC
- Private Subnet
- Route Tables
- Network ACLs (NACLs)

## Key Concepts Covered
- Difference between public and private subnets
- Why private subnets enforce a zero-trust security model
- Why each subnet needs a unique non-overlapping IPv4 CIDR block
- Dedicated route tables for private subnets and why they matter
- Security risks of leaving a private subnet on the main route table
- Custom Network ACL configuration for private subnet isolation
- Difference between default and custom NACL behaviour

## What I Built
- Created a private subnet with a unique CIDR block inside an existing VPC
- Created a dedicated route table with local-only routing for the private subnet
- Detached the private subnet from the main route table to prevent accidental exposure
- Created a custom Network ACL with explicit inbound and outbound rules
- Configured the NACL to allow only internal VPC traffic and block all external access

## Key Learning
The biggest surprise was discovering how open AWS default settings actually are. 
A newly created private subnet automatically attaches to the main route table 
and a default NACL that allows 100% of traffic. AWS gives you the building 
blocks — it is entirely up to you to manually strip away those open defaults and 
build real isolation.

## Documentation
Full project documentation with screenshots available as PDF in this repository.
