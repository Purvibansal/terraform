# Terraform Course

A complete hands-on Terraform learning path designed to take you from beginner to advanced level. This course focuses on real-world AWS infrastructure automation, best practices, modular design, and production-grade workflows.

---

## Day 1: Getting Started with Terraform

#### Introduction to Terraform and IaC

In this session, you'll learn the fundamentals of Terraform and Infrastructure as Code (IaC). We’ll cover:
- What is Infrastructure as Code?
- Why Terraform is widely used
- Benefits of IaC (versioning, automation, consistency, scalability)
- Declarative vs imperative approaches
- How Terraform interacts with cloud provider APIs

By the end of this section, you’ll understand how Terraform fits into modern DevOps workflows.

---

#### Installing Terraform on MacOS, Linux and Windows

Get your hands dirty by installing Terraform on MacOS, Linux, and Windows. This section covers:
- Installing via package managers (brew, apt, choco)
- Manual installation
- Verifying installation
- Setting up PATH
- Terraform CLI basics

---

#### Setting up Terraform for AWS

Dive into AWS integration with Terraform. You’ll learn:
- How Terraform providers work
- Configuring AWS credentials
- IAM user setup and permissions
- Using environment variables
- Setting up the AWS provider block
- Region and version pinning

---

#### Writing Your First Terraform Code

Start writing actual Terraform code with a simple example. You’ll learn:
- Terraform file structure
- Provider blocks
- Resource blocks
- Basic HCL syntax
- Comments and formatting
- Naming conventions

---

### Terraform Lifecycle

Understand the lifecycle of Terraform and what happens behind the scenes:
- `terraform init` – Initialize the project
- `terraform plan` – Preview changes
- `terraform apply` – Apply infrastructure
- `terraform destroy` – Tear down resources

You’ll also learn when and why to use each command.

---

#### Launching an EC2 Instance

Provision your first AWS EC2 instance using Terraform. Topics include:
- Choosing an AMI
- Instance types
- Key pairs
- Security groups
- Tags and naming standards
- Understanding resource dependencies

---

#### Terraform State Basics

Understand the importance of Terraform state files:
- What is terraform.tfstate?
- Desired state vs current state
- Why state matters
- State drift
- Basic state commands
- Risks of local state

---

## Day 2: Advanced Terraform Configuration

#### Understanding Providers and Resources

Deepen your knowledge of providers and resources:
- What is a provider?
- Multiple providers in a project
- Provider versioning
- Resource lifecycle
- Meta-arguments (`depends_on`, `count`, `for_each`)

---

#### Variables and Outputs in Terraform

Learn how to make your configurations dynamic:
- Input variables
- Variable types
- Default values
- tfvars files
- Output blocks
- Sensitive outputs
- Using variables across environments

---

#### Conditional Expressions and Functions

Add logic to your Terraform code:
- Conditional expressions
- Ternary operators
- Built-in functions
- String manipulation
- Math functions
- List and map functions
- Practical use cases

---

#### Debugging and Formatting Terraform Files

Learn how to debug and maintain clean Terraform code:
- `terraform validate`
- `terraform fmt`
- `terraform console`
- Reading error messages
- Debugging failed plans and applies

---

## Day 3: Building Reusable Infrastructure with Modules

#### Creating Modular Infrastructure with Terraform Modules

Understand the power of modular design:
- What are modules?
- Root modules vs child modules
- Why modules matter
- Folder structure
- Module versioning

---

#### Local Values and Data Sources

Simplify and optimize your code:
- What are locals?
- When to use locals
- Data sources explained
- Fetching existing infrastructure
- Referencing external resources

---

#### Using Variables and Inputs with Modules

Learn how to make modules flexible:
- Module inputs
- Passing variables
- Defaults vs required inputs
- Validation rules

---

#### Leveraging Outputs from Modules

Learn how to expose and reuse values:
- Output blocks
- Referencing module outputs
- Chaining modules
- Practical use cases

---

#### Exploring Terraform Registry for Modules

Learn how to use community modules:
- Terraform Registry overview
- How to evaluate module quality
- Version pinning
- Security considerations

---

## Day 4: Collaboration and State Management

#### Collaborating with Git and Version Control

Learn best practices for working with Terraform in teams:
- Git basics
- Branching strategies
- Pull requests
- Code reviews
- Infrastructure versioning

---

#### Handling Sensitive Data and .gitignore

Learn how to secure your Terraform projects:
- What should not be committed
- Using `.gitignore`
- Environment variables
- Secrets management basics

---

#### Introduction to Terraform Backends

Understand how Terraform stores state:
- What is a backend?
- Local vs remote backends
- Benefits of remote backends
- Backend configuration

---

#### Implementing S3 Backend for State Storage

Hands-on setup of remote backend:
- Creating S3 bucket
- Backend configuration
- Migrating state
- Best practices

---

#### State Locking with DynamoDB

Prevent concurrent changes:
- What is state locking?
- Why locking is important
- DynamoDB table setup
- Locking behavior explained

---

## Day 5: Provisioning and Provisioners

#### Understanding Provisioners in Terraform

Learn what provisioners are and when to use them:
- Purpose of provisioners
- Why HashiCorp discourages heavy usage
- Alternatives

---

#### Remote-exec and Local-exec Provisioners

Learn the differences:
- local-exec use cases
- remote-exec use cases
- SSH configuration
- Security considerations

---

#### Applying Provisioners at Creation and Destruction

Learn lifecycle-based automation:
- Create-time provisioners
- Destroy-time provisioners
- Hooks and automation

---

#### Failure Handling for Provisioners

Learn how to handle errors:
- Retry logic
- Timeouts
- `on_failure` attribute
- Debugging failed provisioners

---

## Day 6: Managing Environments with Workspaces

#### Introduction to Terraform Workspaces

Learn how Terraform supports multiple environments:
- What are workspaces?
- Default workspace
- Use cases

---

#### Creating and Switching Between Workspaces

Hands-on workspace management:
- Creating workspaces
- Switching workspaces
- Listing workspaces
- Deleting workspaces

---

#### Using Workspaces for Environment Management

Understand best practices:
- Dev, QA, Prod separation
- Naming conventions
- Risks and limitations
- When NOT to use workspaces

---

## Day 7: Security and Advanced Topics

#### HashiCorp Vault Overview

Learn about secure secrets management:
- What is Vault?
- Why Vault is used
- Secret engines
- Authentication methods
- Token management

---

#### Integrating Terraform with Vault for Secrets

Learn how to securely inject secrets:
- Vault provider
- Reading secrets dynamically
- Avoiding hardcoding secrets
- Secure production patterns

---
