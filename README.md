# Table of contents
1. [Introduction](#introduction)
2. [Some paragraph](#paragraph1)
    1. [Sub paragraph](#subparagraph1)
3. [Another paragraph](#paragraph2)
4. [Another paragraph4](#paragraph4)
    1. [Subcio](#subcio10)

## This is the introduction <a name="introduction"></a>
Some introduction text, formatted in heading 2 style

## Some paragraph <a name="paragraph1"></a>
The first paragraph text

### Sub paragraph <a name="subparagraph1"></a>
This is a sub paragraph, formatted in heading 3 style

## Another paragraph <a name="paragraph2"></a>
The second paragraph text

#### Another paragraph <a name="paragraph4"></a>
The second paragraph text

#### Another paragraph <a name="subcio10"></a>
The second paragraph text


Section 1  - course intro
Section 2 Introduction to cloud Computing
IaaS, PaaS, DaaS, Saas 
IaaS - infrastructure-  storage, compute, VM (EC2s), connectivity, networking, security
PaaS - platform all above plus database sqls servers, aurora etc. with non managed database 
DaaS - database - managed database solution
SaaS - software - office 365, creative cloud etc

OPEX - operational expenditure (own operations or  monthly bill - AWS - elastic)
CAPEX - capital expenditure (equipment, employees, utility bills, static)
 
ways to access AWS:
console
REST API
SDK - software development kits
CLI

Section 3 - Free tier and IAM - Identity and Access Management basics. 
arn - amazon resource name 
Identity and Access Management - IAM
Two type of IAM identities:
IAM users - person that can type in username and password or application that needs permanent access - limited to 5000 users, if more are need - temporary credentials can be implemented within IAM roles 

IAM roles - short lived credentials or virtual users - application, container, microservice, etc - requires temporary access (credentials) - IAM role required to access certain services - read from db , write etc.

Groups - logical grouping - developers, administrators etc, 
Any new user by default has no permissions by default - denied from anything
Authentication - access- username and password - credentials
Authorisation - permission to perform actions - i.e. create new ec2, connect to S3, etc. 
IAM access types:
programmatic - access via anything apart from console - api, cli, sdk or other - access keys needed - access key id and secret access key
console access  - via username and password 
Example: developers mostly need api access, cli or sdk - hence programmatic option - least privileged access practice is most secure approach - give access only needed for a certain role. 
Check option to force new user to change the password at first login. 
IAM Password Policy Screen 
Section 4
VPC intro 
