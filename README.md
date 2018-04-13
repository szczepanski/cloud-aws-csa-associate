<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Introduction](#introduction)
  - [IaaS, PaaS, DaaS, Saas ik](#iaas-paas-daas-saas-ik)
  - [3 Ways to access AWS:](#3-ways-to-access-aws)
  - [Free tier and IAM - Identity and Access Management basics.](#free-tier-and-iam---identity-and-access-management-basics)
    - [Two type of IAM identities:](#two-type-of-iam-identities)
    - [IAM access types:](#iam-access-types)
- [Core Knowledge](#core-knowledge)
  - [VPC - Virtual Private Cloud](#vpc---virtual-private-cloud)
    - [Basic Rules](#basic-rules)
  - [Implied Router and routing tables](#implied-router-and-routing-tables)
    - [Implied Router](#implied-router)
    - [Route Tables](#route-tables)
      - [AWS Reserved Addresses](#aws-reserved-addresses)
    - [Internet Gateway - IGW](#internet-gateway---igw)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->



# Introduction

## IaaS, PaaS, DaaS, Saas ik
- IaaS - infrastructure-  storage, compute, VM (EC2s), connectivity, networking, security
- PaaS - platform all above plus database sql servers, aurora etc. with non managed database
- DaaS - database - managed database solution
- SaaS - software - office 365, creative cloud etc

- OPEX - operational expenditure (own operations or  monthly bill - AWS - elastic)
- CAPEX - capital expenditure (equipment, employees, utility bills, static)

## 3 Ways to access AWS:
- console
- REST API
- SDK (software development kits)
- CLI

## Free tier and IAM - Identity and Access Management basics.
arn - amazon resource name
Identity and Access Management - IAM

### Two type of IAM identities:
- IAM users - person that can type in username and password or application that needs permanent access - limited to 5000 users, if more are need - temporary credentials can be implemented within IAM roles

- IAM roles - short lived credentials or virtual users - application, container, micro-service, etc - requires temporary access (credentials) - IAM role required to access certain services - read from db , write etc.

Groups - logical grouping - developers, administrators etc,
Any new user by default has no permissions by default - denied from anything
Authentication - access- username and password - credentials
Authorisation - permission to perform actions - i.e. create new ec2, connect to S3, etc.

### IAM access types:
- programmatic - access via anything apart from console - api, cli, sdk or other - access keys needed - access key id and secret access key
- console access  - via username and password
Example: developers mostly need api access, cli or sdk - hence programmatic option - least privileged access practice is most secure approach - give access only needed for a certain role.
Check option to force new user to change the password at first login.
IAM Password Policy Screen
Section 4
VPC intro


# Core Knowledge

## VPC - Virtual Private Cloud

VPCs are either for one client all department (large organisations)
Logically isolated form other VPCs

![alt text](https://github.com/szczepanski/cloud-aws-csa-associate/blob/master/media/vpc1.png)


### Basic Rules
- VPCs are region specific - one VPC - one region
- VPC can cover / span across multiple  availability zones
- one or more subnets in single availability zone
- subnets are confined to availability zone - one subnet can not extend / cover multiple availability zones - one subnet to one availability zone
### Components
- CIDR (Classless Inter-Domain Routing) and IP address subnets - RFC1918  - Private ranges:
	- 10.0.0.0        -   10.255.255.255  (10/8 prefix)
	- 172.16.0.0      -   172.31.255.255  (172.16/12 prefix)
	- 192.168.0.0     -   192.168.255.255 (192.168/16 prefix)
- Implied - logical router - by default it sets up routing between subnets within one VPC and towards the Internet Gateway via route tables
- Route tables
- Internet Gateway
- Security Groups  - virtual firewalls configured to protect EC2 instances within a VPC , last defence component in VPC - function within virtual NIC - Elastic Network Interface - ENI / ec2 instance context
- Network Access Control Lists (N-ACLs) , first line of defence, function in subnet / network context
- Virtual Private Gateway use to route traffic from a VPC to outside  own premises, branches via IPsec VPN or direct connection
- IPv6 - all addresses are public, hence AWS can allocate IPv6 address ranges if required.

## Implied Router and routing tables

### Implied Router
Central destination for any VPC routing function.

By default implied router / routing table supports  3 functions (automatically populated, these can not be deleted):
- 	 subnet to subnet routing within single AZ
- 	 routing between different AZs within single VPC.
- 	routing any traffic not matching any configured route table entries to the Internet gateway IGW (connects VPC with Internet)
Each subnet has routing table that routers uses to forward traffic within VPC
Route table can also have information to specific external destinations if required.

### Route Tables
- VPC can have up to 200 route tables
- Single route table can have up to 50 routes /entries
- each subnet **must** be  associated with one only route table - single subnet can not be associated to multiple routing tables
- same / one routing table can be associate to multiple subnets
- if subnet to route table association is not configured, the subnet (when created) will be associated with main (AWS default) VPC route table
- Main route table can not be deleted - to swap main route table, the default table's 'main' flag needs to be unticked. New desired default route table candidate has to be flagged as main. Old main/ default route table can now be deleted.
- every route table in VPC contains default route **allowing all VPC 'subnets to communicate with one another - you can not modify or delete this rule**
### VPC IP Addressing
- once VPC is created its CIDR block can not be changed.
- only way to scale up or down existing VPC CIDR is to migrate it to new VPC with required size CIDR
- minimum AWS configurable CIDR block is /28  (2^4 = 16 hosts)
- maximum size of the VPC CIDR is /16  (2^16 = 65 536 hosts)
- subnets within VPC can not overlap

#### AWS Reserved Addresses

Private ranges (RFC1918)
- 10.0.0.0 - 10.255.255.255 (10/8 prefix)
- 172.16.0.0 - 172.31.255.255 (172.16/12 prefix)
- 192.168.0.0 - 192.168.255.255 (192.168/16 prefix)

Each AWS subnet reserves five addresses.

 10.0.0.0/24 example - 2^8 = 256 => (10.0.0.0 -10.0.0.255):
- Reserved addresses
	- 10.0.0.0 - base network IP
	- 10.0.0.1 - VPC router
	- 10.0.0.2 - DNS related
	- 10.0.0.3 - for future use
	- 10.0.0.255 - last IP (broadcast)

 - Useable range:
	- 10.0.0.4 -10.0.0.254

10.0.0.0/25 example  - 2 ^ 7 = 128 => (10.0.0.0 -10.0.0.127):
- Reserved addresses
	- 10.0.0.0 - base network IP
	- 10.0.0.1 - VPC router
	- 10.0.0.2 - DNS related
	- 10.0.0.3 - for future use
	- 10.0.0.127 - last IP (broadcast)

 - Useable range:
	- 10.0.0.4 -10.0.0.126

### Internet Gateway - IGW
- bridge between VPC, its subnets and Internet
- it is fully managed / provisioned / managed service by AWS - fully scaled, redundant and highly available
-  There is only one IGW per VPC. User can not:
	- see it
	- modify it
	- scale it /add more

- IGW performs NAT (static one to one ) between Private and Public (or elastic).
- IP v4 and v6 support
