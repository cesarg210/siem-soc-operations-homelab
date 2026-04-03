# Elastic Stack Deployment

## 📌 Objective

Deploy and configure a fully functional SIEM using the Elastic Stack to ingest, analyze, and monitor logs from both Linux and Windows systems.

---

## 🧠 Architecture Overview

```
Windows / Linux Endpoints
          ↓
     Elastic Agent
          ↓
     Fleet Server
          ↓
    Elasticsearch
          ↓
        Kibana
```

---

## 🔧 Core Components

### 🐳 Docker (Infrastructure Layer)

* Used to deploy Elasticsearch and Kibana
* Provides isolated, reproducible environments
* Simplifies service management

---

### 🔍 Elasticsearch (Data Engine)

* Stores and indexes logs
* Enables fast querying and searching
* Acts as the SIEM backend

---

### 📊 Kibana (Visualization & Management)

* Web interface for log analysis
* Used to configure Fleet and manage agents
* Displays dashboards and alerts

---

### 🎛️ Fleet (Control Plane)

* Centralized management of Elastic Agents
* Deploys configurations and policies
* Handles agent enrollment

---

### 🧠 Fleet Server

* Installed via Elastic Agent
* Acts as communication hub between agents and Elasticsearch
* Uses secure (HTTPS) communication

---

### 🛰️ Elastic Agents

Installed on:

* Linux server (AD lab environment)
* Windows endpoint

Responsibilities:

* Collect system and authentication logs
* Forward data to Fleet Server

---

## 🔐 Authentication Model

| Token Type       | Purpose                                     |
| ---------------- | ------------------------------------------- |
| Service Token    | Authenticates Fleet Server to Elasticsearch |
| Enrollment Token | Allows endpoints to join Fleet              |

---

## 🌐 Network & Ports

| Service       | Port | Protocol |
| ------------- | ---- | -------- |
| Elasticsearch | 9200 | HTTP     |
| Kibana        | 5601 | HTTP     |
| Fleet Server  | 8220 | HTTPS    |

---

## ⚙️ Deployment Steps

### 1. Deploy Elastic Stack (Docker)
![Docker](../screenshots/docker-compose.png)
* Start Elasticsearch and Kibana containers
* Verify services are reachable

---

### 2. Enable Security

* Configure built-in users
* Set passwords for:

  * `elastic`
  * `kibana_system`

---

### 3. Initialize Fleet

* Access Kibana → Fleet
* Configure Fleet settings

---

### 4. Deploy Fleet Server

![Fleet Server](../screenshots/elastic-agent-server-install.png)

---

### 5. Install Linux Agent

```bash
sudo ./elastic-agent install \
  --url=https://<SIEM-IP>:8220 \
  --enrollment-token=TOKEN \
  --insecure
```

---

### 6. Install Windows Agent

```powershell
.\elastic-agent.exe install `
  --url=https://<SIEM-IP>:8220 `
  --enrollment-token=TOKEN `
  --insecure
```

---

## ✅ Validation
![fleet](../screenshots/elastic-fleet-dashboard.png)
* Fleet Server status: **Healthy**
* Linux Agent: **Healthy**
* Windows Agent: **Healthy**

---

## 🧠 Key Takeaways

* Built a centralized SIEM from scratch
* Implemented secure agent communication (TLS)
* Established log ingestion pipeline for detection
