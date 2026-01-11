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
```

Terraform automatically determines resource relationships and execution flow to ensure your infrastructure is deployed efficiently.

* **Resource dependencies**
* **Order of execution**
* **API calls**

---

## 4. State Management
Terraform maintains a state file (`terraform.tfstate`) that acts as a "source of truth" for your environment. It tracks:

* Existing infrastructure
* Resource dependencies
* Metadata
* Current configuration



### This enables:
* **Drift detection:** Identifying differences between real-world resources and your code.
* **Accurate updates:** Knowing exactly what needs to be changed, added, or deleted.
* **Safer changes:** Reducing the risk of accidental overrides.

### Useful State Commands
| Command | Purpose |
| :--- | :--- |
| `terraform state list` | Lists all resources currently tracked in the state file. |
| `terraform state show <address>` | Shows detailed attributes of a specific resource. |
| `terraform show` | Provides a human-readable output of the entire state. |

### Drift Detection Example
If someone manually deletes a resource from the AWS console, running `terraform plan` will allow Terraform to detect the drift and propose the corrective actions needed to restore the desired state.

---

## 5. Plan and Apply Workflow
Terraform follows a safe and predictable workflow to ensure you are always in control.

1.  **`terraform init`**: Initializes the working directory and downloads providers.
2.  **`terraform plan`**: Shows a preview of the changes Terraform will make.
3.  **`terraform apply`**: Executes the plan to reach the desired state.

> **Benefits:** See what will change, catch mistakes early, and avoid accidental destruction.

---

## 6. Strong Community Support
Terraform has a massive global community, making learning and troubleshooting much easier through:
* Official documentation
* GitHub repositories
* Blogs and tutorials
* StackOverflow answers

---

## 7. Integration with DevOps Tools
Terraform integrates seamlessly with modern DevOps ecosystems:
* **Containers:** Docker, Kubernetes
* **CI/CD:** GitHub Actions, GitLab CI, Jenkins
* **Automation:** Ansible, ArgoCD

### Example: GitHub Actions CI
```yaml
name: Terraform CI
on: [push]

jobs:
  terraform:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: hashicorp/setup-terraform@v2
      - run: terraform init
      - run: terraform plan

```

## 8. HashiCorp Configuration Language (HCL)

Terraform uses **HCL**, which is a domain-specific language designed specifically for managing infrastructure. It provides a balance between human-readability and machine-efficiency.

### Key Characteristics:
* **Human-readable:** Clear syntax that resembles JSON but is easier to write and maintain.
* **Simple to learn:** High-level abstractions mean you don't need to be a programmer to use it.
* **Expressive:** Supports variables, loops, and logic to handle complex environments.

### HCL Example


```hcl
variable "instance_type" {
  description = "The size of the EC2 instance"
  default     = "t2.micro"
}

resource "aws_instance" "web" {
  ami           = "ami-0abcd1234"
  instance_type = var.instance_type

  tags = {
    Name = "HelloWorld"
  }
}
```

## Declarative vs. Imperative

Terraform is **Declarative**, meaning you define the "destination" and Terraform figures out how to get there.



| Feature | Declarative (Terraform) | Imperative (Scripts) |
| :--- | :--- | :--- |
| **Focus** | What you want (End result) | How to do it (Step-by-step) |
| **State** | Desired state awareness | Sequence of commands |
| **Consistency** | **Idempotent** (Safe to run repeatedly) | **Error-prone** (May create duplicates) |
| **Safety** | Safer / Predictable | Risky / Uncertain |
| **Scaling** | Repeatable across environments | Hard to reproduce manually |

---

## Real-World Example

### Without IaC (Manual Process)
* **Login** to AWS Console.
* **Navigate:** Click EC2 → Create Instance.
* **Configure:** Manually select AMI, VPC, and Security Groups.
* **Repeat:** Do this again for Staging, UAT, and Production.
* **Outcome:** Hope nothing breaks and that all settings match.

### With Terraform (IaC)
* **Write:** Define the configuration once in a `.tf` file.
* **Execute:** Run `terraform apply`.
* **Outcome:** **Everything is deployed automatically** and identically every single time.
