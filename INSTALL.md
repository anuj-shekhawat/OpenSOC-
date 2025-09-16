# INSTALL.md

## Assumptions
- AWS VPC with 3 VMs:
  - VM1: ELK (Elasticsearch, Logstash, Kibana)
  - VM2: TheHive, Cassandra, Cortex, MISP
  - VM3: Log generator (Linux/Windows, Snort)
- Ubuntu 20.04/22.04 LTS
---

Ubuntu VM dedicated to ELK SIEM
![AWS Diagram](images/AWspic.png)
---


Inbound Security Rules for ELK SIEM VM
![AWS Diagram1](images/awspi1.png)
---

## Phase 1: ELK

1. Install Java
sudo apt update
sudo apt install -y openjdk-11-jdk

![AWS Diagram1](images/Picture2.png)
----

3. Install Elasticsearch
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
sudo apt install apt-transport-https
echo "deb https://artifacts.elastic.co/packages/8.x/apt stable main" | \
  sudo tee /etc/apt/sources.list.d/elastic-8.x.list
sudo apt update && sudo apt install elasticsearch
sudo systemctl enable --now
elasticsearch

![AWS Diagram1](images/Picture7.png)
----

4. Install Kibana
sudo apt install kibana
sudo systemctl enable --now kibana

![AWS Diagram1](images/Picture8.png)
---


5. Install Logstash / Filebeat
sudo apt install filebeat
sudo systemctl enable --now filebeat

---

## Phase 2: TheHive + Cassandra + Cortex + MISP
1. Cassandra
sudo apt install cassandra
sudo systemctl enable --now cassandra


2. TheHive
sudo apt install thehive
sudo systemctl enable --now thehive


3. Cortex & MISP

Install via official docs.
Integrate Cortex analyzers with TheHive.
Connect MISP as a threat intel source.

