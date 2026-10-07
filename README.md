# 🚀 2-Tier Automated CI/CD Pipeline with Jenkins & NGINX Reverse Proxy

An enterprise-grade, cost-optimized CI/CD deployment architecture simulating AWS multi-tier environments locally using Docker Compose, Jenkins automation engine, and NGINX Reverse Proxy.

---

## 🏗️ Architecture Overview

The system models a dual-tier enterprise architecture isolated within a custom Docker bridge network (vpc_network):

```text
[ Developer Push ] 
        │
        ▼
┌────────────────────────────────────────────────────────┐
│  Tier 1: CI/CD Automation Node                         │
│  - Jenkins Server (:8080)                              │
│  - Docker Engine Integration (/var/run/docker.sock)    │
│  - Automated Build & Deployment Jobs                   │
└───────────────────────┬────────────────────────────────┘
                        │ Container-to-Container Bridge Network
                        ▼
┌────────────────────────────────────────────────────────┐
│  Tier 2: Production Web Tier                           │
│  - NGINX Public Reverse Proxy (:80)                    │
│  - Internal Production Web Server (:80)                │
└────────────────────────────────────────────────────────┘