# ☁️ AWS Cloud Practitioner Study Notes
> Curated notes for the **AWS Cloud Practitioner (CLF-C02)** certification, covering core services, management tools, architectural frameworks, networking, security, storage, pricing, and more.

---

## 📚 Table of Contents

| Module | Topic |
|--------|-------|
| [Module 1](#module-1-core-aws-services--frameworks) | Core AWS Services & Frameworks |
| [Module 2](#module-2-aws-organizations--account-management) | AWS Organizations & Account Management |
| [Module 3](#module-3-aws-support) | AWS Support |
| [Module 4](#module-4-security--identity) | Security & Identity |
| [Module 5](#module-5-networking--content-delivery) | Networking & Content Delivery |
| [Module 6](#module-6-compute) | Compute |
| [Module 7](#module-7-networking-math--important-notes) | Networking Math & Important Notes |
| [Module 8](#module-8-additional-security-services) | Additional Security Services |
| [Module 9](#module-9-storage-services) | Storage Services |
| [Module 10](#module-10-aws-pricing-billing--cloud-economics) | AWS Pricing, Billing & Cloud Economics |

---

## Module 1: Core AWS Services & Frameworks

### 🛠️ Management and Governance Services

AWS provides a suite of services to help you manage, monitor, and govern your resources effectively.

| Service | Description |
|---------|-------------|
| **AWS Trusted Advisor** | Inspects your AWS environment and provides real-time recommendations across 5 categories: cost optimization, performance, security, fault tolerance, and service limits |
| **AWS CloudWatch** | Monitors AWS resources and applications — collects metrics, monitors logs, and sets alarms |
| **AWS CloudTrail** | Records API activity and user actions for governance, compliance, and auditing |
| **AWS Well-Architected Tool** | Reviews workloads against the latest AWS architectural best practices |
| **AWS Auto Scaling** | Automatically adjusts AWS resources to maintain performance and minimize costs |
| **AWS CLI** | Unified tool to manage AWS services from the command line |
| **AWS Config** | Assesses, audits, and evaluates resource configurations to track changes and ensure compliance |
| **AWS Management Console** | Web-based graphical interface for accessing and managing AWS |
| **AWS Organizations** | Centrally govern multiple AWS accounts, consolidate billing, and apply policies |

---

### 🏗️ AWS Cloud Adoption Framework (AWS CAF)

The AWS CAF provides guidance to help organizations build a comprehensive approach to cloud adoption, organized into **six core perspectives**.

#### The Six Core Perspectives

```
┌─────────────────────────────────────────────────────────────┐
│                    AWS CAF Perspectives                      │
├───────────────────────┬─────────────────────────────────────┤
│  Business             │  Align IT with business goals       │
│  People               │  Culture, structure, and roles      │
│  Governance           │  Risk, compliance, IT strategy      │
│  Platform             │  Design & build cloud infra         │
│  Security             │  Security & compliance objectives   │
│  Operations           │  Manage & monitor cloud workloads   │
└───────────────────────┴─────────────────────────────────────┘
```

1. **Business Perspective** — Ensures IT aligns with business needs and drives digital transformation.
   - *Examples: IT Finance, Business Risk Management*

2. **People Perspective** — Prepares HR teams by evolving organizational culture, structure, and roles.
   - *Examples: Training Management, Organizational Change Management*

3. **Governance Perspective** — Aligns IT strategy with business goals, manages risk, and ensures compliance.
   - *Examples: Portfolio Management, License Management*

4. **Platform Perspective** — Helps design, build, and run cloud infrastructure and applications.
   - *Examples: Compute Provisioning, Application Development*

5. **Security Perspective** — Ensures security and compliance objectives are met.
   - *Examples: Identity and Access Management, Data Protection, Incident Response*

6. **Operations Perspective** — Manages, monitors, and operates cloud workloads to meet business requirements.
   - *Examples: Service Monitoring, Business Continuity/Disaster Recovery*

---

## Module 2: AWS Organizations & Account Management

### 🏢 AWS Organizations

AWS Organizations is a central service for managing multiple AWS accounts.

**Key Benefits:**
- Centrally managed access policies using **Service Control Policies (SCPs)**
- Controlled access to AWS services across all accounts
- Automated AWS account creation and management via APIs
- **Consolidated billing** — single bill for all accounts with volume discount benefits

---

### 💰 AWS Billing and Cost Management Tools

| Tool | Purpose |
|------|---------|
| **AWS Billing Dashboard** | High-level view of month-to-date spending, top services by cost, and trends |
| **AWS Budgets** | Set custom budgets and receive alerts when you exceed (or forecast to exceed) thresholds |
| **AWS Cost and Usage Report (CUR)** | Most comprehensive data source — detailed information down to the resource level |
| **AWS Cost Explorer** | Visualization tool to explore data, identify trends, and pinpoint cost drivers |

> 💡 **Tip:** Use Cost Explorer for trend analysis and Budgets for proactive cost alerts.

---

## Module 3: AWS Support

### 🤝 Support Resources

**Technical Account Manager (TAM)**
Primary point of contact for Enterprise Support — provides proactive guidance, architectural reviews, and ongoing communication.

**AWS Trusted Advisor**
Acts as a best-practice expert, providing checks and recommendations customized for your environment.

**AWS Support Concierge**
A billing and account expert (Enterprise plan only) for quick analysis and assistance with non-technical issues.

---

### 📋 Support Plans

| Plan | Best For | Key Features |
|------|----------|--------------|
| **Basic** | All accounts (free) | Whitepapers, documentation, Support Forum |
| **Developer** | Testing / early development | Best-practice guidance, general problem-solving |
| **Business** | Production workloads | Phone/chat support, full Trusted Advisor checks, third-party software support |
| **Enterprise** | Mission-critical workloads | All Business features + TAM, concierge support, Support API |

> 💡 Only **Business** and **Enterprise** plans include a full set of Trusted Advisor checks.

---

## Module 4: Security & Identity

### 🔐 AWS Shared Responsibility Model

Security and compliance is a **shared responsibility** between AWS and the customer.

```
┌─────────────────────────────────────────────────────────────┐
│                    YOUR RESPONSIBILITY                       │
│           Security IN the Cloud (what you build)            │
│  • Guest OS  • App software  • Firewall configs             │
│  • Network ACLs  • Customer data  • Encryption              │
├─────────────────────────────────────────────────────────────┤
│                    AWS RESPONSIBILITY                        │
│           Security OF the Cloud (the foundation)            │
│  • Hardware  • Software  • Networking  • Facilities         │
│  • Physical network  • Regions  • Availability Zones        │
└─────────────────────────────────────────────────────────────┘
```

---

### 👤 AWS Identity and Access Management (IAM)

IAM manages **who** can access **what** in your AWS account.

| IAM Entity | Description |
|------------|-------------|
| **IAM User** | Person or application needing long-term access with permanent credentials |
| **IAM Group** | Collection of IAM users — assign policies to a group, all users inherit permissions |
| **IAM Policy** | JSON document defining which actions are allowed or denied on which resources |
| **IAM Role** | Temporary identity that can be assumed by any entity (service, application, user) that needs it |

**Multi-Factor Authentication (MFA)**
Adds an extra layer of protection — requires username/password + a unique time-based code from a hardware or virtual device.

> 💡 **Best practice:** Never use the root account for daily tasks. Create individual IAM users and use MFA on the root account.

#### IAM Policy Structure (JSON)

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": ["s3:GetObject", "s3:ListBucket"],
      "Resource": "arn:aws:s3:::my-bucket/*"
    }
  ]
}
```

---

## Module 5: Networking & Content Delivery

### 🌐 Amazon Virtual Private Cloud (VPC)

A VPC is a **logically isolated section** of the AWS cloud where you launch resources in a virtual network you define.

- Specific to a **single AWS Region**
- Can span **multiple Availability Zones**

**Subnet** — A range of IP addresses within a VPC, residing in a single AZ.

| Subnet Type | Description |
|-------------|-------------|
| **Public** | Has a direct route to the internet via an Internet Gateway |
| **Private** | No direct internet access — uses NAT Gateway for outbound traffic |

---

### 🔗 VPC Connectivity & Networking

| Service | Purpose |
|---------|---------|
| **Internet Gateway (IGW)** | Allows communication between VPC and the public internet |
| **NAT Gateway** | Enables private subnet instances to reach the internet (outbound only) |
| **VPC Peering** | Private direct connection between two VPCs using private IP addresses |
| **Site-to-Site VPN** | Secure encrypted tunnel between on-premises network and AWS VPC |
| **AWS Direct Connect (DX)** | Dedicated, private, high-bandwidth connection from on-premises to AWS |
| **VPC Endpoints** | Private connection to AWS services (S3, DynamoDB) without internet |
| **AWS Transit Gateway** | Central hub connecting VPCs, VPNs, and Direct Connect connections |

**VPC Peering Restrictions:**
- IP ranges **cannot overlap**
- **Transitive peering is NOT supported** (A→B→C requires A→C direct connection too)

---

### 🔒 VPC Security

#### Security Groups vs Network ACLs

| Feature | Security Groups | Network ACLs |
|---------|----------------|--------------|
| **Level** | Instance level | Subnet level |
| **State** | **Stateful** (return traffic auto-allowed) | **Stateless** (must define both directions) |
| **Rules** | Allow rules only | Allow and Deny rules |
| **Evaluation** | All rules evaluated | Rules evaluated in number order (lowest first) |
| **Default** | Deny all inbound, allow all outbound | Allow all inbound and outbound |

> 💡 **Remember:** Security Groups = Stateful (like a bouncer who remembers you). NACLs = Stateless (like a checkpoint that checks every pass).

---

### 🌍 Global Content Delivery

#### Amazon Route 53
A highly available and scalable **DNS web service** that translates domain names into IP addresses.

**Routing Policies:**

| Policy | Use Case |
|--------|----------|
| **Simple** | Single server environments — route to one resource |
| **Weighted Round Robin** | Distribute traffic by percentage weights |
| **Latency** | Route to the lowest-latency region for the user |
| **Geolocation** | Route based on user's geographic location |
| **Geoproximity** | Route based on resource location with optional bias |
| **Failover** | Active-passive failover to a backup site |
| **Multivalue Answer** | Return up to 8 healthy records selected at random |

---

#### Amazon CloudFront
A fast, global **Content Delivery Network (CDN)** that delivers data, videos, apps, and APIs with low latency.

```
User Request → Edge Location (cache hit? serve it!) 
                     ↓ (cache miss)
             Regional Edge Cache
                     ↓ (cache miss)
             Origin Server (S3, EC2, etc.)
```

- Global network of **edge locations** for popular content
- **Regional edge caches** for less popular content (between edge and origin)
- Self-service model with pay-as-you-go pricing

---

## Module 6: Compute

### 🐳 Container Services

| Service | Description |
|---------|-------------|
| **Amazon ECR** | Fully managed Docker container registry — store, manage, and deploy container images |
| **Amazon ECS** | AWS's own container orchestration tool for running Docker containers |
| **Amazon EKS** | Managed Kubernetes service to run Kubernetes containers on AWS |
| **AWS Fargate** | Serverless compute engine for containers — no EC2 instances to manage |

**AWS Fargate Key Features:**
- Works with both ECS and EKS
- Pay only for vCPU and memory your containers use
- Each task has its own isolation boundary
- Automatically scales based on container requirements
- Ideal when you want to focus on applications, not infrastructure

---

### 💻 Compute Options Comparison

| Service | Type | Best For |
|---------|------|---------|
| **Amazon EC2** | IaaS — Virtual machines | Full control over OS and configuration |
| **AWS Elastic Beanstalk** | PaaS — Managed platform | Fast app deployment without managing infra |
| **AWS Lambda** | Serverless — Function-based | Event-driven, short-duration tasks |
| **Amazon Lightsail** | Simplified VPS | Simple apps, websites, beginners |
| **AWS Batch** | Managed batch computing | Large-scale batch workloads |
| **AWS Outposts** | On-premises AWS | Hybrid cloud, low-latency on-prem needs |
| **VMware Cloud on AWS** | VMware on AWS | Migrate existing VMware workloads |

---

### 🖥️ Amazon EC2 Deep Dive

#### 9 Key Decisions When Launching an EC2 Instance

```
1. Amazon Machine Image (AMI)    — OS and pre-installed software
2. Instance Type                 — CPU, memory, storage, networking
3. Network Settings              — VPC, subnet, public IP
4. IAM Role                      — Permissions for the instance
5. User Data                     — Bootstrap scripts on launch
6. Storage Options               — EBS volumes, instance store
7. Tags                          — Key-value labels for organization
8. Security Group                — Firewall rules
9. Key Pair                      — SSH access credentials
```

#### EC2 Pricing Models

| Model | Description | Best For |
|-------|-------------|---------|
| **On-Demand** | Pay by the hour, no commitments | Unpredictable workloads, testing |
| **Reserved Instances** | 1 or 3 year term, up to 75% discount | Steady-state, predictable workloads |
| **Scheduled Reserved** | Reserve capacity on a recurring schedule | Predictable, time-specific workloads |
| **Spot Instances** | Bid on unused capacity — can be interrupted with 2-min notice | Fault-tolerant, flexible workloads |
| **Dedicated Hosts** | Physical server fully dedicated to you | Compliance, licensing requirements |
| **Dedicated Instances** | Hardware dedicated to single customer | Compliance needs, VPC isolation |

> 💡 **Spot Instances** can be interrupted by AWS with only a **2-minute warning**. Interruption options: terminate, stop, or hibernate.

#### EC2 Monitoring with CloudWatch

| Monitoring Type | Cost | Frequency |
|----------------|------|-----------|
| **Basic** | Free | Metrics every 5 minutes |
| **Detailed** | Fixed monthly rate (7 pre-selected metrics) | Metrics every 1 minute |

---

### ⚡ AWS Lambda Deep Dive

**Truly serverless** — runs code without provisioning or managing servers.

| Feature | Detail |
|---------|--------|
| **Max execution time** | 15 minutes per invocation |
| **Memory** | 128 MB to 10,240 MB (10 GB) |
| **Pricing** | Charged per millisecond of execution |
| **Languages** | Python, Node.js, Java, Go, Ruby, C#, PowerShell, custom runtimes |

**Common Triggers:**
S3 · DynamoDB · API Gateway · CloudWatch Events · SNS · SQS · and more

> 💡 Lambda is ideal for **event-driven applications**, real-time file processing, data transformation, and microservices.

---

### 🌱 AWS Elastic Beanstalk Deep Dive

PaaS — upload your code and Beanstalk handles everything else.

**Supported Platforms:** Java · .NET · PHP · Node.js · Python · Ruby · Go · Docker

**Deployment Options:**

| Option | Description |
|--------|-------------|
| **All-at-once** | Deploy to all instances simultaneously (causes downtime) |
| **Rolling** | Deploy in batches, maintaining partial availability |
| **Rolling with additional batch** | Launch extra instances during deployment |
| **Immutable** | Launch new instances, then swap (safest) |
| **Blue/Green** | Deploy to separate environment, then swap DNS |

> 💡 **No additional charge** for Elastic Beanstalk — pay only for underlying AWS resources.

---

### 💡 Amazon Lightsail

Simplified VPS platform designed for users new to AWS or simple workloads.

- Predictable low monthly pricing (from ~$3.50/month)
- Bundled compute, storage, and data transfer
- Pre-configured stacks: WordPress, Magento, Drupal, Joomla, and more
- One-click SSH access, automatic snapshots
- Can connect to other AWS services via VPC peering

---

## Module 7: Networking Math & Important Notes

### 🔢 IP Address Calculations

**Formula: Number of usable IPs in a subnet**
```
Usable IPs = 2^(32 - CIDR prefix) - 5
```

#### Why Subtract 5? (AWS Reserved IPs per Subnet)

| Reserved IP | Address | Purpose |
|-------------|---------|---------|
| **1st** | x.x.x.0 | Network address |
| **2nd** | x.x.x.1 | VPC router |
| **3rd** | x.x.x.2 | AWS DNS server |
| **4th** | x.x.x.3 | Reserved for future AWS use |
| **Last** | x.x.x.255 | Broadcast address (reserved but not used in VPC) |

#### Quick Reference Table

| CIDR | Total IPs | Usable IPs |
|------|-----------|------------|
| /28 | 16 | 11 |
| /27 | 32 | 27 |
| /26 | 64 | 59 |
| /25 | 128 | 123 |
| /24 | 256 | 251 |
| /23 | 512 | 507 |
| /22 | 1,024 | 1,019 |
| /16 | 65,536 | 65,531 |

#### Example Calculation
```
For a /24 subnet (e.g., 10.0.1.0/24):
  Total IPs  = 2^(32-24) = 2^8 = 256
  Usable IPs = 256 - 5   = 251
```

---

### 📝 Important Networking Notes

- **VPC CIDR block** cannot be changed after creation — plan carefully
- **Subnets** within a VPC cannot overlap in IP ranges
- **Default VPC** is automatically created in each region with public subnets
- A **NAT Gateway** must be in a **public subnet** to work
- **Internet Gateway** is 1-to-1 with a VPC (one IGW per VPC)
- **Security Groups** are stateful; **NACLs** are stateless
- VPC peering does **not** support transitive routing

---

## Module 8: Additional Security Services

### 🛡️ AWS Security Services Overview

| Service | Purpose |
|---------|---------|
| **AWS Shield** | DDoS protection |
| **AWS WAF** | Web Application Firewall — filter malicious web traffic |
| **AWS GuardDuty** | Intelligent threat detection using ML |
| **AWS Inspector** | Automated vulnerability scanning |
| **AWS Macie** | Sensitive data discovery in S3 using ML |
| **AWS Secrets Manager** | Store, rotate, and manage secrets (API keys, passwords) |
| **AWS KMS** | Create and manage cryptographic keys |
| **AWS CloudHSM** | Hardware-based key storage for regulatory compliance |
| **AWS Cognito** | User authentication and authorization for apps |
| **AWS Detective** | Analyze and investigate security findings |
| **AWS Security Hub** | Centralized security findings from multiple AWS services |

---

### 🔰 AWS Shield

Protects against **DDoS (Distributed Denial of Service)** attacks.

| Tier | Cost | Features |
|------|------|---------|
| **Shield Standard** | Free (automatic) | Protection against common layer 3 and 4 attacks |
| **Shield Advanced** | Paid (~$3,000/month) | Layer 7 protection, 24/7 DDoS Response Team (DRT), cost protection, real-time visibility |

---

### 🌐 AWS WAF (Web Application Firewall)

Protects web applications from common web exploits that could affect availability, compromise security, or consume excessive resources.

- Filters traffic based on **rules** (IP addresses, HTTP headers, HTTP body, URI strings)
- Protects against: **SQL injection**, **cross-site scripting (XSS)**, bad bots
- Works with **CloudFront**, **ALB**, **API Gateway**, and **AppSync**
- Supports **managed rule groups** from AWS and AWS Marketplace partners

---

### 🔑 AWS Key Management Service (KMS)

A managed service to **create, manage, and control cryptographic keys** used for data encryption.

- Integrated with most AWS services (S3, EBS, RDS, etc.)
- Supports **automatic key rotation**
- **Customer Managed Keys (CMK)** — you control the key policy
- **AWS Managed Keys** — AWS manages on your behalf
- All key usage is **logged in CloudTrail**

---

### 🔐 AWS Secrets Manager

Securely **store, rotate, manage, and retrieve** secrets like database credentials, API keys, and OAuth tokens.

- Automatic **secret rotation** (e.g., RDS passwords every 30 days)
- Integrated with RDS, Redshift, DocumentDB for native rotation
- Replaces hard-coded credentials in code

> 💡 **Secrets Manager vs SSM Parameter Store:** Secrets Manager is purpose-built for secrets with rotation; Parameter Store is more general-purpose configuration storage.

---

### 🔍 AWS GuardDuty

A continuous **intelligent threat detection** service that analyzes:
- AWS CloudTrail logs
- VPC Flow Logs
- DNS logs

**Detects threats like:**
- Compromised EC2 instances communicating with malicious IPs
- Unusual API calls or account behavior (e.g., from Tor exit nodes)
- Unauthorized deployments of cryptocurrency mining software
- Credential exfiltration attempts

> 💡 GuardDuty requires **no agents** to install — it analyzes existing logs automatically.

---

### 🕵️ AWS Security Hub

A **centralized security dashboard** that aggregates, organizes, and prioritizes security findings from multiple AWS services and third-party tools.

- Integrates with: GuardDuty, Inspector, Macie, IAM Access Analyzer, Firewall Manager
- Provides **automated compliance checks** against standards (CIS, PCI-DSS, AWS Foundational Security)
- Gives a single pane of glass for security posture

---

### 🔒 AWS Certificate Manager (ACM)

Provision, manage, and deploy **SSL/TLS certificates** for AWS services.

- Free public certificates for use with AWS services
- Automatic certificate renewal
- Works with CloudFront, ALB, API Gateway, and more

---

### 🧩 AWS Cognito

Provides **user authentication and authorization** for web and mobile applications.

| Feature | Description |
|---------|-------------|
| **User Pools** | User directory that handles sign-up, sign-in, and user management |
| **Identity Pools** | Grant users temporary AWS credentials to access AWS services directly |

---

## Module 9: Storage Services

### 🗄️ AWS Storage Overview

```
┌──────────────────────────────────────────────────────────────┐
│                    AWS Storage Types                          │
├──────────────────┬───────────────────────┬───────────────────┤
│  Object Storage  │   Block Storage        │  File Storage     │
│  (Amazon S3)     │   (Amazon EBS)         │  (Amazon EFS)     │
│                  │   (Instance Store)     │  (Amazon FSx)     │
└──────────────────┴───────────────────────┴───────────────────┘
```

---

### 🪣 Amazon S3 (Simple Storage Service)

**Object storage** — store any type of file as an object with virtually unlimited capacity.

**Key Concepts:**
- **Buckets** — containers for objects (globally unique names)
- **Objects** — files + metadata, up to **5 TB** per object
- **Keys** — unique identifier for each object within a bucket

#### S3 Storage Classes

| Storage Class | Use Case | Retrieval | Cost |
|--------------|---------|-----------|------|
| **S3 Standard** | Frequently accessed data | Milliseconds | Highest |
| **S3 Intelligent-Tiering** | Unknown or changing access patterns | Milliseconds | Auto-optimized |
| **S3 Standard-IA** | Infrequently accessed, rapid retrieval | Milliseconds | Lower storage |
| **S3 One Zone-IA** | Infrequently accessed, single AZ | Milliseconds | Lowest IA |
| **S3 Glacier Instant** | Archive with instant retrieval | Milliseconds | Very low |
| **S3 Glacier Flexible** | Long-term archive | Minutes to hours | Very low |
| **S3 Glacier Deep Archive** | Longest-term archive | 12–48 hours | Lowest |

#### S3 Key Features

- **Versioning** — keep multiple versions of an object
- **Lifecycle Policies** — automatically transition objects between storage classes
- **Server-Side Encryption (SSE)** — encrypt data at rest (SSE-S3, SSE-KMS, SSE-C)
- **Bucket Policies** — JSON-based access control at the bucket level
- **Access Control Lists (ACLs)** — fine-grained object-level access
- **Static Website Hosting** — host a static website directly from S3
- **Replication** — Cross-Region Replication (CRR) and Same-Region Replication (SRR)
- **Transfer Acceleration** — uses CloudFront edge locations for faster uploads

> 💡 S3 provides **99.999999999% (11 nines)** of durability.

---

### 💾 Amazon EBS (Elastic Block Store)

**Block storage** volumes that attach to EC2 instances — like a virtual hard drive.

| Volume Type | Use Case | Max IOPS |
|------------|---------|----------|
| **gp3** (General Purpose SSD) | Most workloads, baseline performance | 16,000 |
| **gp2** (General Purpose SSD) | General purpose, legacy | 16,000 |
| **io2 / io1** (Provisioned IOPS SSD) | I/O-intensive databases | 64,000 |
| **st1** (Throughput HDD) | Big data, data warehouses | 500 |
| **sc1** (Cold HDD) | Infrequently accessed data | 250 |

**Key Facts:**
- EBS volumes are tied to a **single AZ**
- Can be **snapshotted** to S3 for backup and replication
- Snapshots are **incremental** (only changed blocks are saved)
- Can increase volume size **without downtime**

---

### 📁 Amazon EFS (Elastic File System)

**Managed NFS file system** that can be mounted by multiple EC2 instances simultaneously across AZs.

- **Automatically scales** — no capacity to provision
- **Multi-AZ** access by default (Regional)
- **Storage classes:** EFS Standard, EFS Infrequent Access (IA)
- Accessed via **Mount Targets** (one per AZ)
- Linux-based workloads only (NFS protocol)

> 💡 **EFS vs EBS:** EFS = shared file system (many EC2s). EBS = dedicated block storage (one EC2).

---

### 🏔️ Amazon S3 Glacier

Long-term, low-cost **archival storage** for data that is rarely accessed.

| Option | Retrieval Time |
|--------|---------------|
| **Expedited** | 1–5 minutes |
| **Standard** | 3–5 hours |
| **Bulk** | 5–12 hours |

**Vault Lock** — enforce compliance controls with a locked policy (WORM — Write Once, Read Many).

---

### 🔄 AWS Storage Gateway

Hybrid cloud storage service that connects **on-premises environments to AWS cloud storage**.

| Type | Description |
|------|-------------|
| **File Gateway** | NFS/SMB interface to S3 |
| **Volume Gateway** | iSCSI block storage backed by S3 and EBS snapshots |
| **Tape Gateway** | Virtual tape library backed by S3 Glacier |

---

### ❄️ AWS Snow Family

Physical devices for **data migration** and **edge computing** when internet transfer is impractical.

| Device | Capacity | Use Case |
|--------|----------|---------|
| **Snowcone** | 8 TB usable | Small, portable — rugged edge locations |
| **Snowball Edge Storage** | 80 TB usable | Large data migration, edge storage |
| **Snowball Edge Compute** | 80 TB + GPU | Edge computing + ML |
| **Snowmobile** | Up to 100 PB | Massive data center migration (truck!) |

> 💡 **Rule of thumb:** If data transfer would take more than a week, use Snowball.

---

### 🗂️ Amazon FSx

Fully managed **third-party file systems** on AWS.

| Service | File System | Use Case |
|---------|-------------|---------|
| **FSx for Windows** | Windows File Server | Windows workloads, Active Directory integration |
| **FSx for Lustre** | Lustre | High-performance computing (HPC), ML, media processing |
| **FSx for NetApp ONTAP** | NetApp ONTAP | Enterprise storage features |
| **FSx for OpenZFS** | OpenZFS | Linux-based workloads |

---

## Module 10: AWS Pricing, Billing & Cloud Economics

### 💵 AWS Pricing Fundamentals

AWS follows three fundamental pricing principles:

```
┌─────────────────────────────────────────────────┐
│           AWS Pricing Principles                 │
│                                                  │
│  1. Pay for what you use                         │
│  2. Pay less when you reserve                    │
│  3. Pay less with volume-based discounts         │
└─────────────────────────────────────────────────┘
```

---

### 🧮 Cost Drivers by Service Type

| Category | What You Pay For |
|----------|-----------------|
| **Compute (EC2)** | Instance hours, instance type, OS, region |
| **Storage (S3)** | GB stored per month, requests, data retrieval, transfer out |
| **Data Transfer** | Inbound: FREE · Outbound: charged by GB · Between AZs: charged |
| **Databases (RDS)** | Instance hours, storage, multi-AZ, backups, data transfer |
| **Lambda** | Number of requests + duration (per millisecond) |

> 💡 **Data transfer IN** to AWS is always **free**. **Data transfer OUT** incurs charges.

---

### 🛠️ AWS Pricing Tools

| Tool | Purpose |
|------|---------|
| **AWS Pricing Calculator** | Estimate costs for your planned AWS architecture before you build |
| **AWS Cost Explorer** | Visualize and analyze your actual AWS spend |
| **AWS Budgets** | Set spend thresholds and get alerts |
| **AWS Cost and Usage Report** | Detailed billing data for analysis |
| **AWS Trusted Advisor** | Cost optimization recommendations |

---

### 💰 Ways to Reduce AWS Costs

#### 1. Right Sizing
Match EC2 instance types to your actual workload — avoid over-provisioning.
- Use CloudWatch metrics to identify underutilized instances
- Downsize or terminate idle resources

#### 2. Increase Elasticity
- Use **Auto Scaling** to scale in during low demand
- Schedule scaling for predictable patterns
- Use **Spot Instances** for flexible, fault-tolerant workloads

#### 3. Optimal Pricing Model
- **Reserved Instances** for steady-state workloads (save up to 75%)
- **Savings Plans** for flexible compute usage (save up to 66%)
- **Spot Instances** for batch and fault-tolerant jobs (save up to 90%)

#### 4. Savings Plans

| Type | Flexibility | Savings |
|------|-------------|---------|
| **Compute Savings Plans** | Any instance family, size, region, OS | Up to 66% |
| **EC2 Instance Savings Plans** | Specific instance family in a region | Up to 72% |
| **SageMaker Savings Plans** | SageMaker usage | Up to 64% |

---

### 🌍 AWS Global Infrastructure & Pricing

**Pricing varies by Region** — choose the right region considering:
- Proximity to users (latency)
- Data residency requirements
- Feature availability
- Cost (some regions are cheaper than others)

**AWS Free Tier** — Available for 12 months for new accounts:

| Type | Example |
|------|---------|
| **Always Free** | Lambda (1M requests/month), DynamoDB (25 GB) |
| **12 Months Free** | EC2 (750 hrs/month t2.micro), S3 (5 GB) |
| **Trials** | Short-term free trials for specific services |

---

### 📊 Total Cost of Ownership (TCO)

When comparing on-premises to AWS cloud:

**On-Premises Costs Include:**
- Server hardware purchase and refresh
- Data center facilities (power, cooling, space)
- Network equipment
- IT staff for maintenance
- Software licenses

**AWS Cloud Advantages:**
- No upfront capital expenditure (CapEx → OpEx)
- Pay only for what you use
- Economies of scale
- Reduced operational overhead

> 💡 Use the **AWS TCO Calculator** (now part of AWS Pricing Calculator) to compare on-premises vs. cloud costs.

---

### 📈 AWS Well-Architected Framework

The five pillars of a well-architected AWS workload:

| Pillar | Focus |
|--------|-------|
| **Operational Excellence** | Run and monitor systems, continuously improve |
| **Security** | Protect information, systems, and assets |
| **Reliability** | Recover from failures, meet demand |
| **Performance Efficiency** | Use resources efficiently |
| **Cost Optimization** | Avoid unnecessary costs |
| **Sustainability** *(6th pillar)* | Minimize environmental impact |

---

### 🌐 AWS Compliance & Governance

**AWS Artifact**
Self-service portal to access AWS **compliance reports and certifications**:
- SOC 1, 2, 3
- ISO 27001
- PCI-DSS
- HIPAA
- FedRAMP

**AWS Control Tower**
Automates the setup of a secure **multi-account environment** with guardrails.

**AWS Config**
Continuously evaluates resource configurations against **compliance rules**.

**AWS Audit Manager**
Continuously audits AWS usage to simplify **risk and compliance assessments**.

---

## 🎯 Quick Reference: Key AWS Service Comparisons

### Compute
| Need | Service |
|------|---------|
| Full OS control | EC2 |
| Just deploy code | Elastic Beanstalk |
| Event-driven functions | Lambda |
| Containers without managing servers | Fargate |
| Simple VPS | Lightsail |

### Storage
| Need | Service |
|------|---------|
| Object storage | S3 |
| Block storage for EC2 | EBS |
| Shared file storage | EFS |
| Long-term archival | S3 Glacier |
| Migrate petabytes | Snowball |

### Database
| Need | Service |
|------|---------|
| Relational (MySQL, PostgreSQL) | RDS |
| NoSQL key-value | DynamoDB |
| In-memory cache | ElastiCache |
| Graph data | Neptune |
| Document (MongoDB-compatible) | DocumentDB |
| Immutable ledger | QLDB |

### Security
| Need | Service |
|------|---------|
| User access management | IAM |
| DDoS protection | Shield |
| Web traffic filtering | WAF |
| Threat detection | GuardDuty |
| Vulnerability scanning | Inspector |
| Sensitive data discovery | Macie |
| Encryption keys | KMS |
| Secrets management | Secrets Manager |

---

## 📝 Exam Tips & Tricks

> **Remember the key distinctions:**

- **CloudTrail** = WHO did WHAT (audit log) | **CloudWatch** = HOW is it performing (metrics)
- **Security Groups** = Stateful (instance level) | **NACLs** = Stateless (subnet level)
- **IAM Role** = Temporary, assumable | **IAM User** = Long-term, permanent credentials
- **S3** = Object storage | **EBS** = Block storage | **EFS** = File storage
- **Shield Standard** = Free, automatic | **Shield Advanced** = Paid, with DRT support
- **Direct Connect** = Private, dedicated line | **Site-to-Site VPN** = Encrypted over internet
- **Reserved Instances** = Commit to 1-3 years, save up to 75% | **Spot** = Bid on spare capacity, save up to 90%
- **Fargate** = Serverless containers | **EC2** = You manage servers | **Lambda** = Serverless functions

---

*AWS Cloud Practitioner Study Notes (CLF-C02) • Last updated: 2025*