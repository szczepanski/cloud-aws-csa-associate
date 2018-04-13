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
- [Sample next par](#sample-next-par)
- [Sample Text 2](#sample-text-2)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->



# Introduction 

## IaaS, PaaS, DaaS, Saas ik
IaaS - infrastructure-  storage, compute, VM (EC2s), connectivity, networking, security
PaaS - platform all above plus database sql servers, aurora etc. with non managed database 
DaaS - database - managed database solution
SaaS - software - office 365, creative cloud etc

OPEX - operational expenditure (own operations or  monthly bill - AWS - elastic)
CAPEX - capital expenditure (equipment, employees, utility bills, static)
 
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

# Sample next par 

# Sample Text 2 
