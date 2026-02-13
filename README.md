# AWS Cloud Practitioner Notes

### Module 1: 
## Core AWS Services & Frameworks

### Management and Governance Services
- **AWS Trust Advisor** - Provides real-time guidance to help provision resources following AWS best practices
- **AWS CloudWatch** - Monitors AWS resources and applications
- **AWS CloudTrail** - Tracks user activity and API usage
- **AWS Well-Architected Tool** - Reviews workloads against AWS architectural best practices
- **AWS Auto Scaling** - Automatically scales resources based on demand
- **AWS Command Line Interface** - Manages AWS services through command-line
- **AWS Config** - Assesses, audits, and evaluates resource configurations
- **AWS Management Console** - Web-based interface for AWS management
- **AWS Organizations** - Governs multiple AWS accounts centrally

### AWS Cloud Adoption Framework (CAF)
AWS CAF provides guidance and helps organizations build a comprehensive approach to cloud computing across the organization and throughout the IT lifecycle to accelerate successful cloud adoption.

#### AWS CAF Six Core Perspectives:

**Business Perspective**
- IT Finance
- IT Strategy
- Benefits Realization
- Business Risk Management

**People Perspective**
- Resource Management
- Incentive Management
- Career Management
- Training Management
- Organizational Change Management

**Governance Perspective**
- Portfolio Management
- Program and Project Management
- Business Performance Measurement
- License Management

**Platform Perspective**
- Compute Provisioning
- Network Provisioning
- Storage Provisioning
- Database Provisioning
- System and Solution Provisioning
- Application Development

**Security Perspective**
- Identity and Access Management (IAM)
- Detective Control
- Infrastructure Security
- Data Protection
- Incident Response

**Operations Perspective**
- Service Monitoring
- Application Performance Monitoring
- Resource Inventory Management
- Release Management/Change Management
- Reporting and Analytics
- Business Continuity/Disaster Recovery
- IT Service Catalog

---

### Module 2: 
## AWS Organizations

### Introduction to AWS Organizations
AWS Organizations helps centrally govern multiple AWS accounts.

### Main Benefits of AWS Organizations
- **Centrally managed access policies** across multiple AWS accounts
- **Controlled access** to AWS services
- **Automated AWS account** creation and management
- **Consolidated billing** across multiple AWS accounts

## AWS Billing and Cost Management
- **AWS Billing Dashboard:** Lets u view the status of your month-to-date AWS expenditure, identify the services that account for the majority of your overall expenditure, and understand at a high level costs are trending.
- **AWS Budget:** uses the cost visualization that is provided by cost explorer to show you the status of your budgets and provide forecasts of your estimated costs
- **AWS Cost and Usage Report:** enables you to identify opportunities for optimization by understanding your cost and usage data trends and how you are using your AWS Implementation
- **AWS Cost Explorer:** Includes a default report that visualizes your costs and usage for top cost-incurring AWS services. The monthly running costs report gives you an overview of all your costs for the past 3 months.

## AWS Support
- **Proactive guidance:** Technical Account Manager(TAM):Provide guidance, architectural review, and continuous ongoing communication to keep you informed and prepared as you plan, deploy and optimize your solution.
- **Best Prcatices:** AWS Trust Advisor:ensure that you best practice to increase performance and fault tolerance in the aws enviroment (customized cloud expert)
- **Account assistance:** AWS Support Concierge: A billing expert who provide quick analysis on billing and account issues.

## Support Plan
# Support plan offers four support plans:
- **Basic Support:** Resource Center access, Service Health Dashboard, product FAQs, Discussion forums, and support for health checks
- **Developer Support:** Support for early development on aws
- **Business Support:** Customers that run production workloads
- **Enterprise Support:** Customers that run business and mission-critical workloads

# Module 4:
## AWS Shared Responsibility Model
- **Customer:** platefrom, application, identity and access management, operating system, network, firewalls configuration client side server encryption and data integrity authentication, server side encryption, network traffic protection
- **AWS:** software, compute, storage, Database, networking, hardware, regions, availability zones, edge locations


## AWS Identity and Access Management (IAM)

- **IAM user:** person or application that can authenticate with aws account.
- **IAM Group:** A collection of iam users that are granted identical authorization.
- **IAM Policy:** The document that defines which resources can be accessed and the travel of access to each resource
- **IAM Role:** useful mechanism to grant a set of permissions for making aws servie=ce requests.

important note : iam mfa : in additional yo uset name and password, mfa requires a unique, authentication code to access aws services.


