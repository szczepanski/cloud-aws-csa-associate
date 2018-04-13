Reference:

https://www.udemy.com/aws-certified-solutions-architect-associate-exam/learn/v4/content

# Table of contents

- [Introduction](#introduction)
   - [... aaS and access](#aas)    
   - [IAM Basics](#iambasic)

- [Core Knowledge](#core)
- [Test Paragraph](#paragraph4)

   - [Test Sub](#subcio10)








# Introduction <a name="introduction"></a>

#### IaaS, PaaS, DaaS, Saas <a name="aas"></a>

IaaS - infrastructure-  storage, compute, VM (EC2s), connectivity, networking, security
PaaS - platform all above plus database sqls servers, aurora etc. with non managed database 
DaaS - database - managed database solution
SaaS - software - office 365, creative cloud etc

OPEX - operational expenditure (own operations or  monthly bill - AWS - elastic)
CAPEX - capital expenditure (equipment, employees, utility bills, static)
 
##### 3 Ways to access AWS:
- console
- REST API
- SDK (software development kits)
- CLI

#### Free tier and IAM - Identity and Access Management basics. <a name = "iambasic">
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

# Core Knowledge - VPC,Sec Group,N ACL,Elastic IP,NAT,VPN,VPC Peering& D. Connect <a name="core"></a>
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
VPC intro Groups - logical grouping - developers, administrators etc, 
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
VPC intro Groups - logical grouping - developers, administrators etc, 
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

#### Another p <a name="paragraph4"></a>
The second paragraph text

#### Another sub <a name="subcio10"></a>
The second paragraph text
