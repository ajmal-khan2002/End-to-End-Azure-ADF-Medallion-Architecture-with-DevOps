# End-to-End-Azure-ADF-Medallion-Architecture-with-DevOps
### Production-Grade Data Engineering with CI/CD

---

## Project Overview
Built a complete production-level data engineering pipeline on Microsoft Azure using Azure Data Factory 
(ADF) as the primary orchestration tool.

---
## Note: 

I uploaded images instead of directly connecting the project from Azure DevOps to a Git repository. I attempted the integration, but due to limitations with the free subscription, the connection was not successful. As a result, I shared images of the pipeline instead.

---

## Key Features

### 1. Multi-Source Ingestion
- Azure SQL Database → ADLS Gen2
- CSV flat files → Bronze layer
- On-Premises files via Self-Hosted IR

### 2. Incremental Loading
- Watermark-based pattern
- Lookup + Stored Procedure activities
- Only new/changed records processed
- ~90% reduction in processing time vs full load

### 3. Medallion Architecture (Bronze/Silver/Gold)
- Bronze: Raw data as-is from source
- Silver: Cleaned and validated data
- Gold:   Business-ready aggregated data

### 4. Automated Alerting — Logic Apps
- Pipeline failure triggers email notification
- ADF Web Activity → Logic App → Gmail alert
- Email contains: pipeline name, run ID, error details

### 5. Azure DevOps
- ADF connected to Azure DevOps Git
- ARM Template auto-generated on publish
- Build Pipeline validates ARM template
- Release Pipeline deploys to production
- Branch strategy: feature → dev → main

---

## Tech Stack
| Tool | Purpose |
|------|---------|
| Azure Data Factory | Pipeline orchestration |
| ADLS Gen2 | Data Lake storage |
| Azure SQL Database | Source data |
| Self-Hosted IR | On-premises connectivity |
| Azure Logic Apps | Failure alerting |
| Azure DevOps |
| ARM Templates | Infrastructure as Code |
| GitHub | Version control |

---

## Pipeline Screenshots
### Main Pipeline — Incremental Load
<img width="960" height="436" alt="Screenshot 2026-04-19 165211" src="https://github.com/user-attachments/assets/82c3e863-f719-4723-b89b-2af9f3d3fa7e" />


### Parent Pipeline
<img width="960" height="441" alt="Screenshot 2026-04-19 165300" src="https://github.com/user-attachments/assets/e8248d8d-6988-4a4c-a872-d28609405482" />



### ADLS Gen2 — Bronze/Silver/Gold Layers
<img width="960" height="439" alt="Screenshot 2026-04-19 172744" src="https://github.com/user-attachments/assets/c0b43e8e-6197-4cca-8de6-53648d487ffa" />


### Azure DevOps — Build Pipeline
<img width="958" height="439" alt="Screenshot 2026-04-19 165707" src="https://github.com/user-attachments/assets/4e9e49c2-3417-4abd-bcc0-a05310fda652" />
---

###  Other Image : 
<img width="960" height="438" alt="Screenshot 2026-04-19 165624" src="https://github.com/user-attachments/assets/14b2bde8-7544-4528-b0bb-4995a306d398" />
<img width="960" height="439" alt="Screenshot 2026-04-19 165500" src="https://github.com/user-attachments/assets/7d8649fe-00a8-423d-8ae6-b034a26a1719" />
<img width="960" height="438" alt="Screenshot 2026-04-19 165416" src="https://github.com/user-attachments/assets/1d12485a-3829-4c39-8a91-ff1ea5af0a0f" />
<img width="960" height="438" alt="Screenshot 2026-04-19 165345" src="https://github.com/user-attachments/assets/71972f8b-d724-4f00-b77c-0f72d2e7b2e4" />
<img width="960" height="441" alt="Screenshot 2026-04-19 165300" src="https://github.com/user-attachments/assets/d3547dc3-5706-48c7-9606-cbc2989a8f57" />
<img width="960" height="440" alt="Screenshot 2026-04-19 162448" src="https://github.com/user-attachments/assets/f8b53ea6-a3c1-4983-8ea7-fd7b381cdb31" />
<img width="960" height="439" alt="Screenshot 2026-04-19 162315" src="https://github.com/user-attachments/assets/c6e07769-bf82-4b80-904f-18f235e4435c" />
<img width="1920" height="1080" alt="Screenshot (157)" src="https://github.com/user-attachments/assets/ebf6b08d-80a2-4db8-ad39-1fb4f0d71451" />
<img width="1920" height="1080" alt="Screenshot (156)" src="https://github.com/user-attachments/assets/dd109a9e-c5a9-435a-a42b-37af50573379" />
<img width="1920" height="1080" alt="Screenshot (155)" src="https://github.com/user-attachments/assets/2303894d-f985-4e55-ad49-991a16cd610f" />
<img width="1920" height="1080" alt="Screenshot (154)" src="https://github.com/user-attachments/assets/2c1ee0ca-6d3d-4ef0-bbbb-1dee2f9b3d2b" />
<img width="960" height="326" alt="Screenshot 2026-04-19 171127" src="https://github.com/user-attachments/assets/8e2f0694-07ab-4e77-bb5a-9de3cfa7674c" />

---

## Key Learnings
- Incremental loading with watermark pattern
- Self-Hosted Integration Runtime setup
- Event-driven alerting with Logic Apps
- CI/CD for data pipelines using Azure DevOps
- ARM template parameterization for multi-environment

---

*Built as part of Azure Data Engineering portfolio*
*Tools: Azure | ADF | DevOps | Logic Apps | ADLS Gen2*
