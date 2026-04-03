# 🔵 Phase 3: SIEM Deployment (Elastic Stack)

This phase focuses on deploying a centralized Security Information and Event Management (SIEM) system using the Elastic Stack. The goal is to aggregate logs from multiple systems, establish centralized visibility, and prepare the environment for detection engineering and incident analysis.

---

## ✅ Phase Objectives

• Deploy the Elastic Stack (Elasticsearch, Kibana) using containerization
• Configure centralized log ingestion from Windows and Linux systems
• Establish alerting capabilities for security event detection
• Document security events and prepare for incident response workflows

---

## 🖥️ Lab Environment

Ubuntu Server → Domain Controller (Samba AD)
Ubuntu Server → SIEM Server (Elastic Stack + Fleet Server)
Windows 11 ARM → Domain Workstation
Kali Linux → Attacker Machine

**Internal Lab Network:**

192.168.85.0/24
Domain Controller → 192.168.85.10
SIEM Server → 192.168.85.20
Windows Client → 192.168.85.30

---

## ✍🏽 Focus Areas

### 1. Elastic Stack Installation

The Elastic Stack is deployed using Docker to provide a scalable and isolated environment for SIEM components.

Elasticsearch serves as the data storage and search engine, while Kibana provides the interface for visualization and management. Security features are enabled to enforce authentication and secure communication.

Fleet is configured as the centralized management layer, and Fleet Server is deployed to coordinate communication between agents and the SIEM backend.

---

### 2. Log Ingestion from Windows & Linux

Elastic Agents are installed on both Linux and Windows systems to collect system and authentication logs.

These agents forward telemetry to Fleet Server, which then routes the data into Elasticsearch for indexing and analysis. This establishes centralized visibility across all endpoints in the lab.

---

### 3. Alert Rule Creation

Detection capabilities are introduced by creating alert rules based on ingested log data.

These rules are designed to identify suspicious behavior such as failed authentication attempts, abnormal activity patterns, and potential indicators of compromise.

---

### 4. Incident Documentation

Security events generated within the lab environment are documented to simulate real-world incident response workflows.

This includes capturing relevant logs, identifying key indicators, and outlining response actions to build familiarity with investigative processes.

---

## 💯 Phase Outcome

At the end of this phase the lab environment will have:

• a fully deployed SIEM platform
• centralized log ingestion from multiple endpoints
• foundational detection and alerting capabilities
• documented security events and workflows

This environment will support advanced threat detection and analysis in the next phase.

---
