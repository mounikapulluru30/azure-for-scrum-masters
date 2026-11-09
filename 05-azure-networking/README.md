# Lesson 5: Azure Networking

## Learning Objectives

Understand the main Azure Networking services, their purpose, and how a Scrum Master can recognize networking-related dependencies and connectivity issues that affect application delivery.

## Key Concepts

### 1. What Is Azure Networking?

Azure Networking provides services that enable communication between Azure resources, applications, the internet, and on-premises environments.

Different networking services support requirements such as network isolation, traffic management, secure connectivity, and application availability.

**Key purposes:**
- Connect Azure resources.
- Enable communication between applications and databases.
- Secure network traffic.
- Connect cloud and on-premises environments.
- Distribute incoming application traffic.

### 2. Azure Virtual Network (VNet)

An Azure Virtual Network is a logically isolated private network in Azure that allows resources to communicate with each other and with external networks.

**When to use it:**
- An application requires a private network environment.
- Multiple Azure resources need to communicate.
- An organization needs connectivity between Azure and on-premises networks.

**Key features:**
- Provides network isolation.
- Supports communication between Azure resources.
- Supports subnet creation.
- Enables connectivity with on-premises networks.

**Example:** A banking application uses a VNet to connect its web servers, application servers, and database servers.

**Key consideration:** A VNet provides the foundation for private networking in Azure.

### 3. Azure Subnets

A subnet is a smaller logical network segment within an Azure Virtual Network.

Subnets help organize resources and apply network configurations and security rules.

**When to use it:**
- An application has multiple components that need separate network segments.
- Resources need to be organized based on their roles.
- Network security rules need to be applied to specific segments.

**Example:**
- Frontend Subnet: Web servers.
- Backend Subnet: Application servers.
- Database Subnet: Database resources.

**Key consideration:** Subnets help organize network resources, but they do not automatically provide security isolation. NSGs and other network controls help regulate traffic.

### 4. Network Security Groups (NSGs)

A Network Security Group is an Azure networking feature that filters inbound and outbound network traffic.

**Key concepts:**
- Inbound Rules: Control incoming traffic.
- Outbound Rules: Control outgoing traffic.
- Allow Rules: Permit specified traffic.
- Deny Rules: Block specified traffic.

**When to use it:**
- An application needs restrictions on network access.
- Only authorized sources should access specific resources.
- Certain ports or protocols need to be allowed or blocked.

**Example:** A banking application allows authorized application servers to communicate with database servers while restricting unauthorized access.

**Key consideration:** NSGs can be associated with subnets or network interfaces to control network traffic.

### 5. Public IP and Private IP Addresses

An IP address identifies a resource on a network.

Azure supports public and private IP addresses for different connectivity requirements.

**Public IP Address:**
- Supports internet-facing connectivity.
- Can allow external users to access publicly exposed services.
- Commonly used for public-facing applications.

**Private IP Address:**
- Supports communication within private networks.
- Used for communication between Azure resources and connected private networks.
- Is not directly reachable from the public internet.

**Example:**
- Public IP: Customers accessing a bank's website.
- Private IP: An application server communicating with an internal database.

**Key consideration:** The appropriate IP type depends on the application's connectivity and security requirements.

### 6. Azure VPN Gateway and ExpressRoute

Both services help connect an organization's on-premises network with Azure.

**Azure VPN Gateway:**
- Establishes encrypted connectivity over the internet.
- Connects on-premises networks to Azure VNets.
- Supports secure communication between different environments.

**Azure ExpressRoute:**
- Provides private connectivity between an organization's network and Microsoft cloud services.
- Uses a connectivity provider.
- Does not route traffic over the public internet.
- Supports enterprise connectivity requirements.

**Example:**
- VPN Gateway: An organization securely connects its office network to Azure over the internet.
- ExpressRoute: A large organization connects its datacenter to Azure through a private network connection.

**Key consideration:** VPN Gateway uses encrypted internet connectivity, whereas ExpressRoute provides private connectivity through a connectivity provider.

### 7. Azure Load Balancer

Azure Load Balancer distributes incoming network traffic across multiple backend resources, such as virtual machines.

**Key features:**
- Works at Layer 4 (Transport Layer).
- Supports TCP and UDP traffic.
- Distributes network connections across backend resources.
- Helps improve availability and scalability.

**Example:** An e-commerce application runs on three virtual machines. Azure Load Balancer distributes incoming traffic across these machines.

**Key consideration:** Load Balancer is suitable for distributing network traffic at Layer 4.

### 8. Azure Application Gateway

Azure Application Gateway is a web traffic load balancer that operates at Layer 7 (Application Layer).

**Key features:**
- Supports HTTP and HTTPS traffic.
- Provides URL path-based routing.
- Supports hostname-based routing.
- Supports Web Application Firewall (WAF).
- Helps distribute web requests across backend services.

**Example:**
- `/products` requests are routed to the Product Service.
- `/payments` requests are routed to the Payment Service.

**Key consideration:** Application Gateway supports application-level routing and web application protection features.

### Comparing Azure Networking Services

| Service | Main purpose | Example use case |
|---|---|---|
| Azure VNet | Private network | Connecting Azure resources |
| Subnets | Network segmentation | Separating web, application, and database servers |
| NSG | Traffic filtering | Controlling inbound and outbound traffic |
| Public IP | Internet-facing connectivity | Accessing a public website |
| Private IP | Private network communication | Internal database connectivity |
| VPN Gateway | Encrypted internet connectivity | Connecting an office network to Azure |
| ExpressRoute | Private connectivity | Connecting an enterprise datacenter to Azure |
| Load Balancer | Layer 4 traffic distribution | Distributing TCP/UDP traffic |
| Application Gateway | Layer 7 web traffic routing | URL-based routing and WAF |

These services are not interchangeable. An application might use a VNet for private networking, NSGs for traffic filtering, VPN Gateway for secure connectivity, and Application Gateway for web traffic routing.

## What I Learned

- Azure VNet provides a private networking environment for Azure resources.
- Subnets divide a VNet into smaller logical network segments.
- NSGs control inbound and outbound network traffic.
- Public IP addresses support internet-facing connectivity, while private IP addresses support private network communication.
- VPN Gateway provides encrypted connectivity over the internet.
- ExpressRoute provides private connectivity through a connectivity provider.
- Azure Load Balancer distributes TCP/UDP traffic at Layer 4.
- Azure Application Gateway handles HTTP/HTTPS traffic at Layer 7 and supports URL-based routing and WAF.
- Networking issues can affect application accessibility, integration testing, and release timelines.

## Scrum Master Perspective

A Scrum Master does not need to configure Azure Networking services or solve every technical issue personally. However, understanding the basics helps identify technical dependencies and facilitate effective conversations.

A Scrum Master can:
- Clarify the nature of a networking-related blocker.
- Identify the responsible technical owners, such as developers, network engineers, or cloud/DevOps engineers.
- Understand how the issue affects application access, testing, dependencies, delivery timelines, and the Sprint Goal.
- Facilitate collaboration between the teams involved.
- Make impediments visible and follow up on their resolution.
- Support the team in assessing delivery risks without taking over specialized technical responsibilities.

## Practical Examples and Scenarios

### Scenario 1: Application Cannot Connect to Database

**Situation:** Developers cannot connect to a database hosted in Azure.

**Possible areas to investigate:**
- VNet connectivity.
- Subnet configuration.
- NSG rules.
- IP address configuration.

**Scrum Master response:**
1. Clarify the connectivity issue.
2. Identify the responsible networking and database teams.
3. Facilitate collaboration.
4. Understand the impact on testing and the Sprint Goal.
5. Track the impediment until resolution.

### Scenario 2: Users Cannot Access an Application

**Situation:** Users cannot access an application hosted in Azure.

**Possible areas to investigate:**
- Public IP configuration.
- Network connectivity.
- NSG inbound rules.
- Application Gateway or Load Balancer configuration.

**Scrum Master response:**
1. Understand the issue and affected users.
2. Coordinate with development and infrastructure teams.
3. Identify delivery risks.
4. Track the issue and follow up on resolution.

### Scenario 3: Connecting an On-Premises Datacenter to Azure

**Situation:** An organization wants to connect its on-premises datacenter to Azure.

**Potential options:**
- VPN Gateway for encrypted connectivity over the internet.
- ExpressRoute for private connectivity through a connectivity provider.

**Scrum Master response:**
1. Identify cross-team dependencies.
2. Facilitate discussions between infrastructure and development teams.
3. Make connectivity-related blockers visible.
4. Track dependencies affecting delivery timelines.

### Scenario 4: Application Performance During High Traffic

**Situation:** An application experiences performance issues when many users access it simultaneously.

**Possible areas to investigate:**
- Azure Load Balancer.
- Application Gateway.
- Backend resource capacity.
- Network configuration.

**Scrum Master response:**
1. Understand the performance issue and business impact.
2. Facilitate collaboration between development and cloud teams.
3. Track the issue as an impediment.
4. Monitor its impact on release commitments.

**Key learning:** The Scrum Master enables problem-solving and removes organizational obstacles without needing to perform network configuration personally.

## Interview Questions

1. What is an Azure Virtual Network, and why is it used?
2. What is the difference between a VNet and a subnet?
3. What is a Network Security Group?
4. What is the difference between public and private IP addresses?
5. What is the difference between Azure VPN Gateway and ExpressRoute?
6. What is Azure Load Balancer, and which network layer does it operate at?
7. What is Azure Application Gateway?
8. What is the difference between Azure Load Balancer and Application Gateway?
9. What is URL-based routing?
10. What is the purpose of Web Application Firewall (WAF)?
11. How would you respond if a networking issue blocked application testing during a Sprint?
12. How can a Scrum Master help resolve networking dependencies without taking over the technical team's responsibilities?

## Validation and Reflection

**Validation Score:** 7/10 (70%)

The validation covered:
- Understanding Azure Virtual Networks and subnets.
- Identifying the purpose of Network Security Groups.
- Understanding public and private IP addresses.
- Distinguishing VPN Gateway and ExpressRoute.
- Understanding Azure Load Balancer.
- Understanding Application Gateway and URL-based routing.
- Applying the Scrum Master approach to networking-related impediments.

**Areas to Improve:**
- VPN Gateway vs ExpressRoute.
- Azure Load Balancer vs Application Gateway.
- Application Gateway features, especially URL-based routing and WAF.

**Reflection:** I can now distinguish between the main Azure Networking services and explain how they support communication between Azure resources and external environments. I also understand how networking dependencies can affect application accessibility, testing, and delivery timelines. As a Scrum Master, my responsibility is to facilitate collaboration, make impediments visible, and support the team in resolving delivery challenges rather than taking over specialized technical work.

## Key Takeaways

- Azure VNet provides a private networking environment.
- Subnets organize resources into smaller network segments.
- NSGs control inbound and outbound traffic.
- Public and private IP addresses support different connectivity requirements.
- VPN Gateway provides encrypted connectivity over the internet.
- ExpressRoute provides private connectivity through a connectivity provider.
- Load Balancer distributes TCP/UDP traffic at Layer 4.
- Application Gateway provides Layer 7 web traffic routing and supports WAF.
- Networking dependencies can affect application delivery, testing, and release activities.
- A Scrum Master helps the team make impediments visible, collaborate on resolution, and protect progress toward the Sprint Goal.

## Status

**Completed** — Lesson 5: Azure Networking

Learning cycle: Learn → Practice → Validate → Reflect → Share → Improve
