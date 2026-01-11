# Day 1 – Fundamentals  
## Infrastructure as Code (IaC)

Before the advent of Infrastructure as Code (IaC), infrastructure management was typically a **manual, error-prone, and time-consuming** process. System administrators and operations teams had to perform most tasks manually, which introduced inconsistencies, delays, and operational risks.

---

## Challenges Before IaC

1. **Manual Server Configuration**  
   Servers and infrastructure components were configured manually, often using UI-based tools or shell access. This led to:
   - Human errors
   - Inconsistent environments
   - Configuration drift
   - Lack of repeatability

2. **Lack of Version Control**  
   Infrastructure configurations were not stored in version control systems like Git, making it:
   - Hard to track changes
   - Difficult to roll back
   - Impossible to audit history

3. **Documentation Heavy**  
   Organizations relied heavily on documentation to record setup steps. Over time:
   - Docs became outdated
   - Knowledge was lost
   - Manual steps were skipped

4. **Limited Automation**  
   Automation was limited to basic scripts that lacked:
   - Idempotency
   - Dependency management
   - Error handling
   - Scalability

5. **Slow Provisioning**  
   Creating new environments took days or weeks due to:
   - Manual approvals
   - Sequential steps
   - Human intervention

---

## What is Infrastructure as Code (IaC)?

Infrastructure as Code (IaC) is the practice of managing and provisioning infrastructure using **machine-readable configuration files**, rather than manual processes or UI-based tools.

With IaC:
- Infrastructure is defined using code
- Stored in Git repositories
- Reviewed like application code
- Automatically deployed
- Versioned
- Reproducible
- Auditable

---

## Benefits of IaC

IaC solves traditional infrastructure challenges by offering:

### ✅ Consistency  
Same infrastructure across all environments (dev, QA, prod).

### ✅ Speed  
Provision infrastructure in minutes, not days.

### ✅ Reliability  
Reduces human errors.

### ✅ Version Control  
Track, audit, and roll back changes.

### ✅ Scalability  
Scale infrastructure with simple configuration updates.

### ✅ Automation  
Enable fully automated deployments.

---

## Popular IaC Tools

Some widely used Infrastructure as Code tools include:

- **Terraform** – Multi-cloud, declarative, state-based
- **AWS CloudFormation** – AWS-native IaC
- **Azure ARM Templates / Bicep**
- **Pulumi**
- **Ansible** (Configuration Management)

These tools enable organizations to define, deploy, and manage infrastructure efficiently and consistently.

---

# Why Terraform?

Terraform is one of the most popular IaC tools today. Below are the key reasons why Terraform is widely adopted across the industry.

---

## 1. Multi-Cloud Support

Terraform is cloud-agnostic. It supports:

- AWS
- Azure
- Google Cloud
- Kubernetes
- GitHub
- Databases
- SaaS platforms
- On-premise infrastructure

This flexibility is ideal for:
- Multi-cloud strategies
- Hybrid cloud environments
- Cloud migrations

---

## 2. Large Ecosystem

Terraform has a massive ecosystem of:

- Providers
- Official modules
- Community modules
- Verified modules

All of these are available through the **Terraform Registry**, saving time and encouraging reuse.

---

## 3. Declarative Syntax

Terraform uses a **declarative** approach. You define *what you want*, not *how to do it*.

Example:

```hcl
resource "aws_instance" "example" {
  ami           = "ami-0abcd1234"
  instance_type = "t2.micro"
}
