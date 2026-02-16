# AWS Cloud Practitioner Study Notes

> Curated notes for the AWS Cloud Practitioner (CLF-C02) certification, covering core services, management tools, architectural frameworks, networking, and security.

---

## Table of Contents

- [Module 1: Core AWS Services & Frameworks](#module-1-core-aws-services--frameworks)
- [Module 2: AWS Organizations & Account Management](#module-2-aws-organizations--account-management)
- [Module 3: AWS Support](#module-3-aws-support)
- [Module 4: Security & Identity](#module-4-security--identity)
- [Module 5: Networking & Content Delivery](#module-5-networking--content-delivery)
- [Module 6: Compute](#module-6-compute)
- [Module 7: Networking Math & Important Notes](#module-7-networking-math--important-notes)
- [Module 8: Additional Security Services](#module-8-additional-security-services)

---

## Module 1: Core AWS Services & Frameworks

### Management and Governance Services

AWS provides a suite of services to help you manage, monitor, and govern your resources effectively.

**AWS Trusted Advisor**  
A digital advisor that inspects your AWS environment and provides real-time recommendations in five categories: cost optimization, performance, security, fault tolerance, and service limits.

**AWS CloudWatch**  
A monitoring service for AWS resources and applications. It collects and tracks metrics, collects and monitors log files, and sets alarms.

**AWS CloudTrail**  
Records API activity and user actions in your account. It enables governance, compliance, and operational and risk auditing.

**AWS Well-Architected Tool**  
Helps you review the state of your workloads and compares them to the latest AWS architectural best practices.

**AWS Auto Scaling**  
Automatically adjusts the number of AWS resources (like EC2 instances) to maintain performance and minimize costs during demand changes.

**AWS Command Line Interface (CLI)**  
A unified tool to manage your AWS services from the command line, allowing for automation and scripting.

**AWS Config**  
A service that assesses, audits, and evaluates the configurations of your AWS resources, allowing you to track changes and ensure compliance.

**AWS Management Console**  
A web-based, graphical interface for accessing and managing your AWS account and services.

**AWS Organizations**  
Allows you to centrally govern multiple AWS accounts, consolidate billing, and apply policies for security and automation.

### AWS Cloud Adoption Framework (AWS CAF)

The AWS CAF provides guidance to help organizations build an effective and comprehensive approach to cloud adoption. It organizes guidance into six core perspectives, each covering distinct responsibilities.

#### The Six Core Perspectives

1. **Business Perspective**  
   Ensures that IT aligns with business needs and that investments drive digital transformation and business goals.  
   *Examples: IT Finance, Business Risk Management*

2. **People Perspective**  
   Helps HR and people management teams prepare for cloud adoption by evolving organizational culture, structure, and roles.  
   *Examples: Training Management, Organizational Change Management*

3. **Governance Perspective**  
   Focuses on skills and processes to align IT strategy with business goals, manage risk, and ensure compliance.  
   *Examples: Portfolio Management, License Management*

4. **Platform Perspective**  
   Helps you design, build, and run your cloud infrastructure and applications.  
   *Examples: Compute Provisioning, Application Development*

5. **Security Perspective**  
   Ensures that your organization meets its security and compliance objectives.  
   *Examples: Identity and Access Management, Data Protection, Incident Response*

6. **Operations Perspective**  
   Helps you manage, monitor, and operate your cloud workloads to meet business requirements.  
   *Examples: Service Monitoring, Business Continuity/Disaster Recovery*

---

## Module 2: AWS Organizations & Account Management

### AWS Organizations

AWS Organizations is a central service for managing multiple AWS accounts. Its main benefits include:

- Centrally managed access policies using **Service Control Policies (SCPs)**
- Controlled access to AWS services across all accounts
- Automated AWS account creation and management via APIs
- Consolidated billing to get a single bill for all accounts and take advantage of volume discounts

### AWS Billing and Cost Management Tools

**AWS Billing Dashboard**  
Provides a high-level view of your month-to-date spending, top services by cost, and cost trends.

**AWS Budgets**  
Allows you to set custom budgets (monthly, quarterly) for costs or usage and receive alerts when you exceed (or are forecasted to exceed) your thresholds.

**AWS Cost and Usage Report (CUR)**  
The most comprehensive data source for your AWS costs and usage. It provides detailed information down to the resource level, which can be used for in-depth analysis.

**AWS Cost Explorer**  
A visualization tool that includes default reports (e.g., top services by cost) and allows you to explore your data, identify trends, and pinpoint cost drivers.

---

## Module 3: AWS Support

### Support Resources

**Technical Account Manager (TAM)**  
A primary point of contact for Enterprise Support, providing proactive guidance, architectural reviews, and ongoing communication to help you plan and optimize your solutions.

**AWS Trusted Advisor**  
Acts as a best-practice expert, providing checks and recommendations customized for your environment.

**AWS Support Concierge**  
A billing and account expert available for the Enterprise Support plan to provide quick analysis and assistance with non-technical issues.

### Support Plans

| Plan | Description | Key Features |
|------|-------------|--------------|
| **Basic** | Free for all accounts | Access to whitepapers, documentation, and Support Forum |
| **Developer** | Recommended for testing or early development | Best-practice guidance and support for general guidance and problem-solving |
| **Business** | Ideal for running production workloads | Direct phone/chat support, full set of Trusted Advisor checks, support for third-party software |
| **Enterprise** | For business and mission-critical workloads | All Business features + designated TAM, concierge support team, Support API |

---

## Module 4: Security & Identity

### AWS Shared Responsibility Model

Security and compliance are a shared responsibility between AWS and the customer. This model helps reduce the customer's operational burden.

**Customer (Security IN the Cloud)**  
The customer is responsible for security within the cloud. This includes:
- Managing the guest operating system
- Application software
- Firewall configurations
- Network ACLs
- Customer data

**AWS (Security OF the Cloud)**  
AWS is responsible for the security of the cloud infrastructure that runs all the services. This includes:
- Hardware, software, networking, and facilities
- AWS services infrastructure
- Physical network (Regions and Availability Zones)

### AWS Identity and Access Management (IAM)

IAM is the service for managing access to AWS resources securely.

**IAM User**  
A person or application that requires long-term access to your AWS account. It has permanent credentials.

**IAM Group**  
A collection of IAM users. Instead of defining permissions for each individual user, you can assign policies to a group, and all users in the group inherit those permissions.

**IAM Policy**  
A document written in JSON that defines permissions. It specifies which actions (e.g., `ec2:start`, `s3:listbucket`) are allowed or denied on which AWS resources.

**IAM Role**  
An identity within an account with specific permissions. It is not uniquely associated with one person; instead, it can be assumed by any entity that needs it temporarily, like an AWS service or an application running on an EC2 instance.

**Multi-Factor Authentication (MFA)**  
An optional but highly recommended security feature that adds an extra layer of protection. In addition to a username and password, users must enter a unique, time-based code from a hardware or virtual device.

---

## Module 5: Networking & Content Delivery

### Amazon Virtual Private Cloud (VPC)

A VPC is a logically isolated section of the AWS cloud where you can launch AWS resources in a virtual network that you define. It is specific to a single AWS region but can span multiple Availability Zones (AZs).

**Subnet**  
A range of IP addresses within a VPC. Subnets reside in a single AZ and are classified as either public (with direct route to the internet) or private (no direct internet access).

**Elastic IP Address**  
A static, public IPv4 address that can be allocated to your account and remapped to any instance or network interface in the same region, masking instance failures.

### VPC Connectivity & Networking

**Internet Gateway (IGW)**  
A highly available and redundant component that allows communication between your VPC and the public internet. It is attached to the VPC and acts as a target for internet-bound traffic from public subnets.

**NAT Gateway (Network Address Translation)**  
A managed service that enables instances in a private subnet to connect to the internet or other AWS services for updates or patches, but prevents the internet from initiating a connection with them.

**VPC Peering**  
A private, direct network connection between two VPCs that allows routing traffic using private IPv4 or IPv6 addresses. Instances in peered VPCs behave as if they were on the same network.

*Restrictions:*
- IP ranges cannot overlap
- Transitive peering (e.g., VPC A → VPC B → VPC C) is not supported; a full mesh of connections is required

**AWS Site-to-Site VPN**  
A secure connection that links your on-premises network or office to your AWS VPC over the public internet, using encrypted tunnels.

**AWS Direct Connect (DX)**  
A service that establishes a dedicated, private, and high-bandwidth network connection between your on-premises data center and AWS. This can reduce costs, increase reliability, and provide a more consistent experience than internet-based connections.

**VPC Endpoints**  
Allow you to privately connect your VPC to supported AWS services (like S3 or DynamoDB) without requiring a public IP address or traffic to traverse the internet. They are powered by AWS PrivateLink.

**AWS Transit Gateway**  
Acts as a central network hub. You can connect your VPCs, VPN connections, and AWS Direct Connect connections to a single gateway, which simplifies network management and reduces the number of complex peering relationships.

### VPC Security

#### Security Groups

Act as a virtual, **stateful** firewall for an instance (e.g., an EC2 instance). They control inbound and outbound traffic at the instance level.

- **Stateful**: If you allow inbound traffic on a port, the outbound return traffic is automatically allowed, regardless of outbound rules
- The default security group denies all inbound traffic and allows all outbound traffic

#### Network Access Control Lists (Network ACLs)

Act as a **stateless** firewall for a subnet. They control traffic entering and exiting the subnet.

- **Stateless**: You must explicitly define rules for both inbound and outbound traffic. Return traffic is not automatically allowed
- Rules are evaluated by number (lowest to highest) to determine whether traffic is allowed or denied

### Global Content Delivery

**Amazon Route 53**  
A highly available and scalable Domain Name System (DNS) web service. It translates human-readable domain names (like example.com) into IP addresses used by computers to connect.

**Amazon CloudFront**  
A fast, global content delivery network (CDN) service. It securely delivers data, videos, applications, and APIs to customers globally with low latency and high transfer speeds by using a network of edge locations.

#### Route 53 Supported Routing Policies

- **Simple routing**: Use for single-server environments to route traffic to a single resource
- **Weighted round robin routing**: Assign weights to resource record sets to specify the frequency of traffic distribution
- **Latency routing**: Help improve your global applications by routing traffic based on the lowest network latency for the user
- **Geolocation routing**: Route traffic based on the geographic location of your users
- **Geoproximity routing**: Route traffic based on the geographic location of your resources, with optional bias to shift more traffic to a specific location
- **Failover routing**: Fail over to a backup site if your primary site becomes unreachable (active-passive failover)
- **Multivalue answer routing**: Respond to DNS queries with up to eight healthy records selected at random to improve availability

#### CloudFront: Fast, Global, and Secure CDN Service

- Global network of edge locations and regional edge caches
- Self-service model
- Pay-as-you-go pricing
- **Edge locations**: Network of data centers that CloudFront uses to serve popular content quickly to customers
- **Regional edge caches**: CloudFront locations that cache content that is not popular enough to stay in an edge location. They are located between the origin server and the global edge locations

---

## Module 6: Compute

### Container Services

**Amazon ECR (Elastic Container Registry)**  
A fully-managed Docker container registry to store, manage, and deploy container images.

**Amazon ECS (Elastic Container Service)**  
AWS's own container orchestration tool for running and managing Docker containers.

**Amazon EKS (Elastic Kubernetes Service)**  
Managed Kubernetes service for AWS to run Kubernetes containers.

**AWS Fargate**  
A serverless compute engine for containers that reduces administrative overhead. You don't need to manage the underlying servers. It can run containers for either ECS or EKS.

### Compute Options

**VMware Cloud on AWS**  
Allows you to migrate and run your VMware workloads on AWS with consistent operations.

**Amazon EC2 (Elastic Compute Cloud)**  
Infrastructure as a Service (IaaS), instance-based, virtual machines that you can provision and manage as you choose.

**EC2 Auto Scaling**  
Automatically adjusts the number of EC2 instances to maintain performance and minimize costs.

**AWS Elastic Beanstalk**  
Platform as a Service (PaaS) for fast and easy application deployment. You upload code and it automatically handles capacity provisioning, load balancing, and scaling.

**AWS Lambda**  
Serverless computing, function-based, low cost. Write and deploy code that runs on schedule or is triggered by events. Use when possible when architecting for the cloud.

**Amazon Lightsail**  
Easy-to-use virtual private server (VPS) for simple applications and websites.

**AWS Batch**  
Run batch computing workloads at any scale.

**AWS Outposts**  
Run AWS infrastructure and services on-premises for a truly consistent hybrid experience.

**AWS Serverless Application Repository**  
A managed repository for serverless applications.

### EC2 Nine Key Decisions When Launching

1. Amazon Machine Image (AMI)
2. Instance type
3. Network settings
4. IAM role
5. User data
6. Storage options
7. Tags
8. Security group
9. Key pair

### EC2 Pricing Models

| Model | Description | Use Case |
|-------|-------------|----------|
| **On-Demand** | Pay by the hour/second, no commitment | Short-term, irregular workloads |
| **Savings Plans** | Low price for 1- or 3-year commitment to consistent usage ($/hour) | Predictable workloads with flexibility |
| **Reserved Instances** | Low price for 1- or 3-year commitment to specific instance family in specific region | Steady-state workloads |
| **Spot Instances** | Request unused EC2 capacity, save up to 90%, can be interrupted with 2-minute warning | Fault-tolerant or stateless workloads |
| **Dedicated Hosts** | Physical server dedicated for your use | Server-bound software licensing requirements |

### Elastic IP Address

A static, public IPv4 address that can be allocated to your account and remapped.

**Key difference from public IP**: Public IPs change when an instance stops and starts; Elastic IPs are static and remain with your account until you release them.

---

## Module 7: Networking Math & Important Notes

### IP Address Calculations

**Number of IPs in a subnet:**

```
2^(32 - CIDR) - 5
```

#### Why subtract 5?

AWS reserves 5 IP addresses per subnet automatically:

1. **Network address**: First IP (e.g., 10.0.0.0)
2. **VPC router**: Second IP (.1) - For internal routing
3. **AWS DNS**: Third IP (.2) - Base of the VPC DNS server
4. **AWS Future use**: Fourth IP (.3) - Reserved by AWS
5. **Broadcast address**: Last IP (.255) - Broadcast is not supported in VPC but address is still reserved

---
