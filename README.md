# Open SOC — ELK + TheHive/Cortex + MISP (Proof of Concept)

This repository documents a personal proof-of-concept Open SOC built on **Ubuntu VMs in AWS**.

**Project author:** Poonam Agarwal  
**Scope:** Single VPC with 2 primary VMs + separate log generator VM (Linux/Windows/Snort).  
**Phase 1 (completed):** ELK (Elasticsearch, Logstash, Kibana) on VM1 — SIEM ingestion, dashboards, rule tuning.  
**Phase 2 (in progress):** TheHive + Cassandra + Cortex + MISP on VM2 — alert management, case response, enrichment.

## Repository structure
