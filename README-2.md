<div align="center">

  <h1>🔐 Uber Credentials Management System</h1>
  <p><b>A Zero-Trust, High-Scale Secrets Management & Authorization Framework</b></p>

  <!-- Badges -->
  <img src="https://img.shields.io/badge/Security-Zero--Trust-black?style=for-the-badge&logo=shield" alt="Security" />
  <img src="https://img.shields.io/badge/Architecture-Microservices-0052CC?style=for-the-badge&logo=uber" alt="Architecture" />
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" alt="License" />

</div>

---

## 📌 Overview

This project implements a secure, scalable **Credentials Management System** inspired by Uber's infrastructure. Designed to handle secrets, API keys, and dynamic access policies across distributed microservices, it minimizes attack surfaces through automated key rotation, dynamic authorization, and strict RBAC.

---

## ✨ Key Features

* 🛡️ **Zero-Trust Architecture:** Strict identity verification for every service request.
* 🔄 **Automated Secret Rotation:** Dynamic lifecycle management for database keys and API tokens without downtime.
* 🔑 **Role-Based Access Control (RBAC):** Fine-grained permissioning across microservices.
* 📊 **Audit Logging & Compliance:** Immutable access logs for monitoring and security audits.
* ⚡ **High-Availability Storage:** Fast secret retrieval with caching and encrypted persistent storage.

---

## 🏗️ Architecture Workflow

```text
┌────────────────┐      1. Authenticate       ┌────────────────────────┐
│  Microservice  │ ─────────────────────────► │ Credentials Manager    │
│  (Client App)  │                            │ (Auth & Policy Check)  │
└───────┬────────┘                            └───────────┬────────────┘
        │                                                 │
        │ 3. Access Resource                              │ 2. Issue Dynamic
        ▼                                                 │    Temporary Token
┌────────────────┐                                        │
│ Internal API / │ ◄──────────────────────────────────────┘
│ Database       │
└────────────────┘
