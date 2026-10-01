# ☁️ Lesson 1 — Azure & Cloud Fundamentals

**Status:** ✅ Completed
**Validation Score:** 48/50 — **96%**

---

## 🎯 Learning Objectives

The objective of this lesson was to build a foundational understanding of:

* Cloud computing
* Microsoft Azure
* Infrastructure as a Service (IaaS)
* Platform as a Service (PaaS)
* Software as a Service (SaaS)
* Basic cloud-based application delivery
* Azure deployment concepts
* The Scrum Master's role when technical cloud issues affect delivery

The focus was **not** on becoming an Azure engineer.

The goal was to understand enough technical terminology and concepts to communicate effectively with engineering teams and facilitate Agile delivery.

---

# ☁️ 1. What is Cloud Computing?

Cloud computing means using computing resources such as:

* Servers
* Storage
* Databases
* Networking
* Applications
* Other IT services

over the internet instead of managing all the underlying infrastructure ourselves.

Cloud platforms can provide these resources on demand and allow organizations to scale them according to their needs.

### Scrum Master Perspective

A Scrum Master does not need to manage cloud infrastructure.

However, understanding cloud concepts can help when:

* A development environment is unavailable
* A deployment is blocked
* A technical dependency affects the Sprint
* Teams need infrastructure support
* UAT or Production deployment is delayed

---

# 🔷 2. What is Microsoft Azure?

**Microsoft Azure is Microsoft's cloud computing platform that provides services for building, running, storing, securing, monitoring, and deploying applications.**

Azure provides a wide range of services that organizations can use for:

* Compute
* Storage
* Databases
* Networking
* Security
* Monitoring
* Application development
* Deployment

### Scrum Master Perspective

I don't need to know every Azure service.

Instead, I should understand the basic terminology well enough to:

* Follow technical conversations
* Identify potential dependencies
* Understand delivery impediments
* Ask meaningful questions
* Facilitate communication between relevant people

---

# 🏗️ 3. IaaS — Infrastructure as a Service

**IaaS stands for Infrastructure as a Service.**

With IaaS, organizations can rent infrastructure resources such as:

* Virtual Machines
* Networking
* Storage

instead of purchasing and maintaining the physical infrastructure themselves.

### Simple Example

```text
Traditional Infrastructure
        ↓
Company owns/manages physical servers

IaaS
        ↓
Cloud provider provides infrastructure
        ↓
Organization configures and manages what it needs
```

### Scrum Master Perspective

IaaS is useful to understand when technical teams discuss:

* Virtual machines
* Infrastructure dependencies
* Server availability
* Network issues
* Infrastructure provisioning

---

# 🧩 4. PaaS — Platform as a Service

**PaaS stands for Platform as a Service.**

PaaS provides a managed platform that developers can use to build, run, and deploy applications without managing all the underlying infrastructure themselves.

### Simple Comparison

```text
IaaS
↓
Infrastructure is provided

PaaS
↓
Infrastructure + platform capabilities are provided

Developer
↓
Focuses more on application development
```

### Scrum Master Perspective

Understanding PaaS helps when developers discuss:

* Application hosting
* Managed platforms
* Deployment environments
* Platform dependencies

---

# 💻 5. SaaS — Software as a Service

**SaaS stands for Software as a Service.**

With SaaS, users access a ready-to-use software application rather than managing the underlying infrastructure or platform.

### Example

**Microsoft 365** is a common example of SaaS.

Other familiar SaaS applications include many browser-based business and productivity applications.

### Simple Comparison

| Model | What is provided? | Typical user focus           |
| ----- | ----------------- | ---------------------------- |
| IaaS  | Infrastructure    | Infrastructure configuration |
| PaaS  | Platform          | Application development      |
| SaaS  | Software          | Using the application        |

---

# 🔄 6. IaaS vs PaaS vs SaaS

A simplified way to remember the models:

```text
IaaS → Infrastructure
PaaS → Platform
SaaS → Software
```

As we move from IaaS → PaaS → SaaS, the cloud provider manages more of the underlying infrastructure and platform, while the customer manages less.
### Key Learning

I understood the difference as:

> **IaaS provides infrastructure, PaaS provides a platform to build/run applications, and SaaS provides ready-to-use software.**

---

# 🚦 7. Practical Scrum Master Scenario

### Situation

The team has completed development work, but the application cannot be deployed to UAT because the Azure pipeline is failing.

As a Scrum Master, I don't need to fix the pipeline myself.

Instead, I can help the team investigate the delivery impact.

### Questions I would ask

#### Where is the failure occurring?

* Build?
* Testing?
* Deployment?

#### What could be causing the failure?

* Application issue?
* Configuration issue?
* Environment issue?
* Permission issue?
* Infrastructure issue?

#### Are there dependencies?

* Does another team need to provide support?
* Is another system involved?
* Is the environment available?
* Is access or approval required?

#### What is the delivery impact?

* Is testing blocked?
* Is the Sprint Goal affected?
* Are other User Stories dependent on this deployment?
* Is there a risk to the planned Increment?

### Scrum Master Response

My role could include:

1. Make the impediment visible.
2. Facilitate communication between the relevant people.
3. Help identify dependencies.
4. Understand the impact on the Sprint Goal.
5. Follow up on the impediment.
6. Ensure the team has the necessary support to move forward.

---

# 🧠 8. What I Learned About the Scrum Master Role

One of my key takeaways from this lesson is:

> A Scrum Master does not need to solve every technical problem, but should understand enough about the technical environment to facilitate effectively.

For example, if a deployment is blocked, simply saying:

> "The deployment is blocked."

provides limited context.

A better understanding allows me to ask:

> "Where is the pipeline failing, what dependency is causing the issue, who needs to collaborate, and what is the impact on the Sprint Goal?"

This helps make the impediment more transparent and actionable.

---

# 📝 9. Validation

After studying the concepts, I validated my understanding through questions and practical scenarios.

### Validation Result

**48 / 50 — 96%**

### Areas Validated

* Azure fundamentals
* IaaS
* PaaS
* SaaS
* Cloud concepts
* Azure deployment scenarios
* Technical impediment identification
* Scrum Master response to technical delivery issues

The validation helped confirm that I understood the concepts rather than simply reading definitions.

---

# 🔍 10. What I Improved During Validation

During the validation process, I refined my understanding of:

### Azure

Instead of thinking of Azure simply as a collection of cloud resources, I refined the definition to:

> **Microsoft Azure is Microsoft's cloud computing platform that provides services for building, running, storing, securing, monitoring, and deploying applications.**

### SaaS

I initially used ChatGPT as an example of SaaS.

The concept was correct, but for conventional Azure/cloud interview discussions, I learned that examples such as **Microsoft 365** are more appropriate and easier to communicate in a standard cloud context.

### Deployment Troubleshooting

I expanded my initial questions about a failed UAT deployment to also consider:

* Dependencies
* Environment availability
* Permissions
* Infrastructure
* Impact on the Sprint Goal
* Impact on dependent work

---

# 💡 11. Key Takeaways

### 1. Cloud computing

Cloud computing provides access to computing resources and services without organizations necessarily managing the underlying physical infrastructure themselves.

### 2. Azure

Azure is Microsoft's cloud computing platform.

### 3. IaaS

Infrastructure such as virtual machines, networking, and storage is provided as a service.

### 4. PaaS

A managed platform is provided for building and running applications.

### 5. SaaS

Ready-to-use software is provided to users.

### 6. Scrum Master relevance

A Scrum Master benefits from understanding technical concepts well enough to:

* Facilitate conversations
* Identify impediments
* Understand dependencies
* Ask useful questions
* Communicate delivery impact
* Support the team without taking over technical responsibilities

---

# 🎯 Interview Questions I Practiced

### Q1. What is Microsoft Azure?

**Answer:**

Microsoft Azure is Microsoft's cloud computing platform that provides services for building, running, storing, securing, monitoring, and deploying applications.

---

### Q2. What is IaaS?

**Answer:**

IaaS, or Infrastructure as a Service, provides infrastructure resources such as virtual machines, networking, and storage through the cloud.

---

### Q3. What is the difference between IaaS and PaaS?

**Answer:**

IaaS provides infrastructure resources, while PaaS provides a managed platform that allows developers to build and run applications without managing all the underlying infrastructure.

---

### Q4. What is SaaS?

**Answer:**

SaaS, or Software as a Service, provides ready-to-use software applications to users over the internet.

A common example is Microsoft 365.

---

### Q5. A deployment to UAT is failing. What would you do as a Scrum Master?

**Answer:**

I would first help the team understand where the failure is occurring, such as during build, testing, or deployment. I would facilitate collaboration with the appropriate technical people, identify dependencies and impediments, understand the impact on testing and the Sprint Goal, and follow up until the impediment is addressed.

I would not try to solve the technical issue myself unless it falls within my responsibilities.

---

# 🔄 Learning Cycle

This lesson followed the learning approach used throughout this repository:

```text
Learn
  ↓
Practice
  ↓
Validate
  ↓
Reflect
  ↓
Share
  ↓
Improve
```

---

# 📌 Lesson Status

**✅ Completed**

**Validation Score: 48/50 — 96%**

---
