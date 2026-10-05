# ☁️ Lesson 2 — Azure Architecture

> **Status:** ✅ Completed
> **Validation Score:** 9.5/10 — **95%**

## 🎯 Learning Objectives

In this lesson, I learned the core Azure architecture concepts and how they relate to application delivery:

* Azure Regions
* Availability Zones
* Azure Subscriptions
* Resource Groups
* Azure Resources
* Access and permissions
* How Azure architecture decisions can create delivery dependencies and impediments
* How a Scrum Master can facilitate resolution without needing to perform the technical configuration

---

# 1. Azure Regions 🌍

An **Azure Region** is a geographic perimeter containing a set of Azure datacenters.

A region can influence architectural decisions related to:

* Latency
* Data residency
* Compliance
* Availability
* Disaster recovery
* Cost
* Service availability

### Scrum Master Perspective

A Scrum Master does not decide which Azure region should be used.

However, understanding regions helps the Scrum Master recognize when a region-related decision can create:

* Technical dependencies
* Deployment constraints
* Testing issues
* Delivery risks
* Compliance concerns

### Example

If a team cannot deploy a required service because that service is unavailable in the selected region, the Scrum Master should help make the dependency visible, identify the appropriate owner, understand the delivery impact, and facilitate collaboration toward resolution.

---

# 2. Availability Zones ⚡

An **Availability Zone** is a separated group of datacenters within an Azure region.

Each availability zone has independent:

* Power
* Cooling
* Networking infrastructure

Availability Zones are designed to improve resilience by separating workloads across physically distinct locations within a region.

### Region vs Availability Zone

| Concept                         | Meaning                                                          |
| ------------------------------- | ---------------------------------------------------------------- |
| **Region**                      | Geographic area containing Azure datacenters                     |
| **Availability Zone**           | Separate group of datacenters within a region                    |
| **Multiple Regions**            | Can provide protection against regional-level failures           |
| **Multiple Availability Zones** | Can provide resilience against certain datacenter-level failures |

> **Important:** Availability Zones are not a general solution for a cross-region problem. They operate within a region.

### Scrum Master Perspective

The Scrum Master does not design the availability-zone architecture.

The Scrum Master's role is to understand when such architecture decisions create dependencies or delivery risks.

For example:

> "The application deployment is waiting because the database configuration for the required availability-zone setup is not ready."

The Scrum Master can help identify:

* Who owns the dependency?
* Is testing blocked?
* Is the Sprint Goal at risk?
* What support is required?
* When can the dependency be resolved?

---

# 3. Azure Subscriptions 💳

An **Azure Subscription** is a management and billing boundary within Azure.

A simplified view is:

```text
Azure
   ↓
Subscription
   ↓
Resource Group
   ↓
Azure Resources
```

Organizations may use different subscriptions for different environments, business units, applications, or governance requirements.

### Example

```text
Company Azure
│
├── Development Subscription
├── Test Subscription
└── Production Subscription
```

> This is an example organizational structure, not a mandatory Azure configuration.

### Scrum Master Perspective

A subscription can become relevant when the team encounters issues involving:

* Access
* Deployment
* Governance
* Resource availability
* Environment configuration

For example:

> "The application is ready, but the team cannot deploy to the required subscription."

The Scrum Master should help identify the owner of the dependency and understand its impact on delivery.

---

# 4. Resource Groups 📦

A **Resource Group** is a logical container for related Azure resources.

Example:

```text
Resource Group: LearningApp-Test

├── Web App
├── Database
├── Storage Account
├── Application Service
└── Monitoring Resource
```

Resource Groups help organize and manage related resources.

### Scrum Master Perspective

Suppose the development environment works but the test environment is missing a required Azure resource.

Instead of simply recording:

> "Testing is blocked."

A Scrum Master can facilitate better questions:

* Which resource is missing?
* Why is it required?
* Who owns it?
* Why hasn't it been provisioned?
* Is there a dependency on another team?
* What is the impact on the Sprint Goal?

---

# 5. Azure Resources 🔧

An **Azure Resource** is an individual item that is created and managed in Azure.

Examples include:

* Virtual Machines
* Storage Accounts
* Databases
* Virtual Networks
* App Services
* Azure Functions
* Key Vaults

The simplified relationship is:

```text
Azure
   ↓
Subscription
   ↓
Resource Group
   ↓
Resources
```

Microsoft identifies subscriptions, resource groups, and resources as core components of Azure's management infrastructure.

---

# 6. Access & Permissions 🔐

A technical delivery problem may sometimes appear to be an Azure architecture problem when the actual issue is **access or permissions**.

For example:

> "The developer needs to delete an Azure resource but doesn't have permission."

The first question should be:

> **Who is authorized to perform this action, and what permission is required?**

The Scrum Master does not change the permission themselves.

Instead, the Scrum Master can help:

1. Understand why the action is required.
2. Identify the resource owner.
3. Identify the appropriate cloud/platform/security team.
4. Understand whether the restriction is due to access control or governance.
5. Assess the delivery impact.
6. Facilitate resolution or an agreed alternative.

### Key distinction

| Concept               | Question                                                       |
| --------------------- | -------------------------------------------------------------- |
| **Region**            | Where is the infrastructure geographically located?            |
| **Availability Zone** | How can workloads be separated within a region for resilience? |
| **Subscription**      | Which management/billing boundary does it belong to?           |
| **Resource Group**    | How are related resources logically organized?                 |
| **Resource**          | What Azure component is being used?                            |
| **Permissions**       | Who is allowed to perform an action?                           |

---

# 7. Scrum Master Perspective 🧭

Azure architecture knowledge does **not** mean the Scrum Master needs to become an Azure engineer.

The goal is to understand enough technical context to ask better questions and facilitate delivery effectively.

### Without technical context

> "Deployment is blocked."

### With basic Azure understanding

> "Which Azure resource is causing the deployment dependency, who owns it, and what impact does the dependency have on testing and the Sprint Goal?"

This helps the Scrum Master connect:

```text
Technical Issue
      ↓
Dependency
      ↓
Impediment
      ↓
Delivery Impact
      ↓
Facilitation
      ↓
Resolution / Follow-up
```

---

# 8. Practical Scenario 1 — Missing Azure Resource

### Situation

Development is complete, but the team cannot deploy to the test environment because a required Azure resource has not been provisioned.

### Scrum Master Investigation

I would investigate:

* What exact resource is missing?
* Why is it required?
* Why has it not been provisioned?
* Is the issue related to the subscription, resource group, region, permissions, or another dependency?
* Who owns the dependency?
* What is the impact on testing?
* Is the Sprint Goal at risk?

### Scrum Master Action

I would:

* Make the impediment visible.
* Identify the appropriate owner/team.
* Facilitate collaboration between the Scrum Team and the concerned technical teams.
* Discuss delivery impact with the Product Owner when relevant.
* Follow up until the blocker is resolved or an agreed alternative is identified.

---

# 9. Practical Scenario 2 — Different Azure Regions

### Situation

The application works in Development, but deployment to Test fails because the environments are configured in different Azure regions.

### Scrum Master Investigation

I would first understand:

* Why are the environments in different regions?
* Is the difference actually causing the failure?
* Are there service availability or compatibility considerations?
* Are there latency, compliance, data residency, or security considerations?
* Can the architecture be changed safely?
* What teams own the dependency?

Being in different regions is **not automatically a problem**. The impact depends on the workload, services, business requirements, and architecture. Region and availability-zone choices can affect reliability, performance, cost, compliance, and operational complexity.

### Scrum Master Action

I would:

* Make the issue visible.
* Identify the relevant technical owner.
* Facilitate collaboration among the involved teams.
* Assess the impact on testing, Sprint Goal, and release.
* Discuss significant delivery impact with the Product Owner.
* Follow up until resolution or an agreed alternative is reached.

---

# 10. Practical Scenario 3 — Permission Issue

### Situation

A developer needs to delete an Azure resource but does not have permission.

### Investigation

The primary issue is an **access/permission problem**.

I would investigate:

* Why does the resource need to be deleted?
* Is deletion actually necessary?
* Who owns the resource?
* Who has the required permission?
* Is the restriction related to security or governance?
* What impact does the delay have on delivery?

### Scrum Master Action

I would identify the appropriate resource owner or cloud/platform/security team, facilitate collaboration, assess delivery impact, and follow up until the required action or an agreed alternative is available.

---

# 11. Interview Questions 🎤

### Q1. What is an Azure Region?

**Answer:**

An Azure Region is a geographic perimeter containing a set of Azure datacenters. Region selection can affect factors such as latency, compliance, data residency, availability, cost, and service availability.

### Q2. What is an Availability Zone?

**Answer:**

An Availability Zone is a physically separated group of datacenters within an Azure region, with independent power, cooling, and networking. It is used to improve resilience and availability.

### Q3. What is the difference between a Subscription and a Resource Group?

**Answer:**

A Subscription is a management and billing boundary in Azure, while a Resource Group is a logical container used to organize related Azure resources.

### Q4. Does a Scrum Master need to know how to configure Azure?

**Answer:**

No. The Scrum Master needs enough understanding of Azure concepts to communicate effectively with technical teams, identify dependencies and impediments, understand delivery impact, and facilitate resolution.

### Q5. A deployment is blocked because an Azure resource is missing. What would you do as Scrum Master?

**Answer:**

I would understand the missing resource and the reason it is required, identify the dependency owner, assess the impact on testing and the Sprint Goal, make the impediment visible, facilitate collaboration with the appropriate technical teams, and follow up until the issue is resolved or an agreed alternative is available.

---

# 12. What I Learned 💡

* Azure Regions represent geographic locations containing Azure datacenters.
* Availability Zones provide physical separation within a region to improve resilience.
* Subscriptions provide management and billing boundaries.
* Resource Groups logically organize related Azure resources.
* Azure Resources are the actual services/components used by applications.
* Permissions determine what users or teams are authorized to do.
* Azure architecture decisions can create dependencies and delivery risks.
* A Scrum Master does not need to configure Azure but should understand enough to ask meaningful questions and facilitate resolution.

---

# 13. Scrum Master Takeaway 🧭

> **I don't need to be the Azure engineer. I need to understand enough Azure architecture to recognize dependencies, ask better questions, connect the right people, and understand how technical issues affect delivery.**

---

# 14. Validation & Reflection

### Validation Score

**9.5/10 — 95% ✅**

### Reflection

Through practical scenarios, I validated my understanding of:

* Region vs Availability Zone
* Subscription vs Resource Group
* Azure Resources
* Access/Permission issues
* Technical dependencies
* Delivery risks
* Sprint Goal impact
* Scrum Master facilitation

One important learning was that I should **investigate the actual root cause before assuming that a Region, Availability Zone, Subscription, or Resource Group is responsible for an issue**.

The focus should be:

> **Understand → Investigate → Identify Dependency → Assess Impact → Facilitate → Follow Up**

---

# 🔄 Learning Cycle

**Learn → Practice → Validate → Reflect → Share → Improve**

---

## 📌 Status

**Lesson 2 — Azure Architecture: ✅ Completed**

**Validation Score: 9.5/10 — 95%**
