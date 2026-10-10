# Lesson 3: Azure Compute

## Learning Objectives

Understand the main Azure Compute services, their use cases, and how a Scrum Master can recognize compute-related dependencies and impediments that affect delivery.

## Key Concepts

### 1. What Is Azure Compute?

Azure Compute refers to Azure services that provide processing capability to run applications, execute code, and handle workloads.

Different compute services are designed for different requirements, such as hosting web applications, running code in response to events, controlling a server operating system, or packaging applications with their dependencies.

### 2. Azure Virtual Machines (VMs)

An Azure Virtual Machine is a virtual computer hosted in Azure. It provides resources such as CPU, memory, storage, and an operating system.

**When to use it:**
- An application requires specific operating-system settings.
- Custom software must be installed directly on the server.
- A legacy application requires greater server-level control.

**Key consideration:** The team has more responsibility for operating-system configuration, patching, maintenance, and security.

### 3. Azure App Service

Azure App Service is a managed hosting service for web applications and APIs.

**When to use it:**
- A team needs to host a web application or API.
- Developers want to focus on application development and deployment.
- The team wants Azure to manage much of the underlying hosting infrastructure.

**Key consideration:** App Service reduces infrastructure management compared with running an application directly on a VM, but it does not provide the same level of operating-system control.

### 4. Azure Functions

Azure Functions is a serverless compute service that runs code in response to events or triggers.

Examples include:
- Processing a file when it is uploaded.
- Running a scheduled task.
- Processing a message or responding to an application event.

**Key consideration:** Serverless does not mean that servers do not exist. Azure manages the underlying infrastructure, allowing the team to focus on the code and its behavior.

### 5. Containers

Containers package an application and its dependencies together so that it can run more consistently across environments.

For example, a team can package an application and its required libraries to reduce differences between a developer's machine and a test environment.

**Key concepts:**
- A container image is the package or template used to create a container.
- A container is a running instance of an image.
- Containers generally share the host operating-system kernel and are different from full virtual machines.
- Azure Container Apps is one option for running containerized applications without managing the underlying infrastructure directly.
- Azure Kubernetes Service (AKS) provides Kubernetes-based container orchestration.

**Key consideration:** Containers can improve consistency, but they do not eliminate the need for configuration management, testing, monitoring, or troubleshooting.

## Comparing Azure Compute Options

| Service | Main purpose | Example use case |
|---|---|---|
| Azure Virtual Machines | Virtual servers with OS-level control | Legacy application requiring custom OS configuration |
| Azure App Service | Managed hosting for web applications and APIs | Hosting an online shopping website |
| Azure Functions | Event-driven code execution | Processing an order when an event occurs |
| Containers | Packaging applications and dependencies | Running an application consistently across environments |

These options are not always mutually exclusive. For example, an application might use App Service for its web interface and Azure Functions for background processing.

## What I Learned

- Azure Compute provides different ways to run applications and execute code.
- Virtual Machines are useful when greater operating-system control is required.
- App Service is suitable for managed web application and API hosting.
- Azure Functions is useful for event-driven workloads.
- Containers package applications and their dependencies to improve consistency across environments.
- The best option depends on the application's requirements, infrastructure control, deployment needs, and operational responsibilities.

## Scrum Master Perspective

A Scrum Master does not need to configure Azure resources or solve every technical issue personally. However, understanding the basics of Azure Compute helps identify technical dependencies and facilitate effective conversations.

A Scrum Master can:

- Clarify the nature of a technical blocker.
- Identify the responsible technical owners, such as developers or cloud/DevOps engineers.
- Understand how the issue affects testing, dependencies, delivery timelines, and the Sprint Goal.
- Facilitate collaboration between the teams involved.
- Make impediments visible and follow up on their resolution.
- Support the team in assessing delivery risks without taking over specialized technical responsibilities.

## Practical Examples and Scenarios

### Scenario 1: Choosing a Compute Service

**Situation:** A team needs to host a web application without managing virtual machines.

**Appropriate option:** Azure App Service.

**Reason:** It provides managed hosting for web applications and APIs.

### Scenario 2: Legacy Application Requirements

**Situation:** An application requires a specific operating-system configuration and custom software installed directly on the server.

**Appropriate option:** Azure Virtual Machines.

**Reason:** VMs provide greater control over the guest operating system and server configuration.

### Scenario 3: Event-Driven Processing

**Situation:** An online store needs to process a file or order event automatically.

**Appropriate option:** Azure Functions.

**Reason:** Functions can execute code in response to configured events or triggers.

### Scenario 4: Application Consistency

**Situation:** An application works on a developer's machine but encounters environment differences during testing.

**Potential approach:** Package the application and its dependencies in a container.

**Reason:** Containers help reduce differences between environments. The team must still validate configuration, connectivity, permissions, and deployment settings.

### Scenario 5: Deployment Failure Blocking Testing

**Situation:** A deployment fails because of an environment configuration issue. Testing is blocked, and the Sprint Goal may be at risk.

**Scrum Master response:**
1. Clarify what is failing and gather relevant information.
2. Identify the responsible technical owners.
3. Facilitate collaboration to investigate and resolve the issue.
4. Make the impediment and its delivery impact visible.
5. Follow up and help the team assess the impact on the Sprint Goal.

**Key learning:** The Scrum Master enables problem-solving and removes organizational obstacles without needing to perform the technical configuration personally.

## Interview Questions

1. What is Azure Compute, and why are different compute services available?
2. What is the difference between Azure Virtual Machines and Azure App Service?
3. When would you use Azure Functions?
4. What are containers, and how do they help application delivery?
5. How would you respond if an Azure deployment issue blocked testing during a Sprint?
6. How can a Scrum Master help resolve technical dependencies without taking over the technical team's responsibilities?

## Validation and Reflection

**Validation Score:** 5/5 (100%)

The validation covered:
- Selecting the appropriate compute service for managed web hosting.
- Identifying when operating-system-level control is required.
- Recognizing event-driven processing use cases.
- Understanding the benefit of packaging applications and dependencies in containers.
- Applying the Scrum Master approach to a cloud-related impediment.

**Reflection:** I can now distinguish between the main Azure Compute options and explain how technical environment issues can affect testing and Sprint delivery. I also understand the Scrum Master's role in facilitating collaboration and making impediments visible rather than taking over specialized technical work.

## Key Takeaways

- Choose the compute service according to the application's needs.
- Understand the trade-off between infrastructure control and managed services.
- Containers help improve consistency but do not remove the need for testing.
- Technical dependencies can affect delivery even when the Scrum Master is not responsible for configuring the technology.
- A Scrum Master helps the team make impediments visible, collaborate on resolution, and protect progress toward the Sprint Goal.

## Status

**Completed** — Lesson 3: Azure Compute

Learning cycle: Learn → Practice → Validate → Reflect → Share → Improve
