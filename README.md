# Open SOC — ELK + TheHive + Cortex + MISP 

This repository documents a personal proof-of-concept Open SOC built on **Ubuntu VMs in AWS**.

**Project author:** Anuj Shekhawat  
**Scope:** Single VPC with 2 primary VMs + separate log generator VM (Linux/Windows/Snort).  
**Phase 1 (completed):** ELK (Elasticsearch, Logstash, Kibana) on VM1 — SIEM ingestion, dashboards, rule tuning.  
**Phase 2 (in progress):** TheHive + Cassandra + Cortex + MISP on VM2 — alert management, case response, enrichment.

## Repository structure
```text
opensource-soc/
├── README.md
├── INSTALL.md
├── architecture_diagram.png
└── screenshots/
    ├── poc_screenshot_1.png   # Cassandra running (systemctl)
    └── poc_screenshot_2.png   # TheHive running (systemctl)
