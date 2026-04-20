# End-to-End Azure Data Pipeline (ADF & DevOps)

A production-grade, event-driven data pipeline orchestrated with Azure Data Factory and Azure DevOps, implementing the Medallion Architecture (Bronze/Silver/Gold) on ADLS Gen2.

---

## 🏗️ Architecture & CI/CD Design

This project focuses on operational excellence, featuring incremental load patterns and CI/CD automation.

### Pipeline Flow

**Documentation Note:**  
This repository utilizes visual architectural captures of the ADF environment. This approach is adopted to illustrate the end-to-end pipeline design and configuration logic without exposing sensitive environment-specific service connections or private credentials.

---

## ⚙️ Key Engineering Features

- **Incremental Loading:**  
  Implemented a watermark-based pattern using Lookup and Stored Procedure activities. This reduced pipeline processing time by approximately 90% compared to full-load strategies.

- **Medallion Architecture:**  
  Standardized data flow from Bronze (raw landing) → Silver (validated/cleansed) → Gold (business-ready).

- **CI/CD Integration:**  
  Full Azure DevOps integration. ARM templates are automatically generated on publish and validated through build pipelines for multi-environment deployment.

- **Event-Driven Alerting:**  
  Decoupled alerting system using Azure Logic Apps. ADF failures trigger a Web Activity, sending detailed error diagnostics to stakeholders via email.

---

## 🛠 Tech Stack

| Category        | Tools                          |
|----------------|--------------------------------|
| Orchestration  | Azure Data Factory             |
| Storage        | ADLS Gen2                      |
| Connectivity   | Self-Hosted IR                 |
| CI/CD          | Azure DevOps, ARM Templates    |
| Alerting       | Azure Logic Apps               |

---

## 🚀 Key Learnings

- **Performance:**  
  Designing watermark patterns is critical for cost-optimization and reducing compute overhead in large-scale pipelines.

- **Resilience:**  
  Building automated alerting systems (Logic Apps) is a non-negotiable requirement for production-grade data engineering.

- **DevOps:**  
  Parameterizing ARM templates is the key to moving code seamlessly from Dev to Prod environments.
