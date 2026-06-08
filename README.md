<img width="1024" height="559" alt="027cac90-fa1b-455f-b242-6f7c3ff76d26" src="https://github.com/user-attachments/assets/43da0dd6-9389-4019-858d-7f6ac193ccdf" />

# Enterprise Infrastructure Observability Mesh

A production-ready, low-latency infrastructure observability stack engineered to provide deep telemetry, centralized log aggregation, and proactive alerting across microservices. 

This project implements an isolated virtual network mesh to collect, index, and visualize system metrics and container logs with zero-downtime reconfiguration capability.

## 🏗️ Architecture & Technology Stack

- **Metrics Telemetry:** Prometheus & Prometheus Node Exporter (Kernel-level hardware metrics gathering).
- **Log Aggregation:** Grafana Loki (High-performance, metadata-indexed log ingestion).
- **Visualization & Alerting:** Grafana (Centralized intelligence dashboard with real-time alerting thresholds).
- **Container Orchestration:** Docker & Docker Compose (Isolated bridge network configuration).

## 🚀 Quick Start

### Prerequisites
Ensure the Grafana Loki Docker Driver is installed globally on your host system:
bash
docker plugin install grafana/loki-docker-driver:latest --alias loki --grant-all-permissions

Deployment
1- Clone the repository:
git clone <your-repository-url>
cd Enterprise_Infrastructure_Observability_Mesh

2-Fire up the observability mesh:
docker compose up -d

3-Access the services:
Grafana Dashboard: http://localhost:3000

Prometheus TSDB: http://localhost:9090

Loki Endpoint: http://localhost:3100/ready

🚨 Alerting Strategy
The stack includes a proactive alerting profile configured under the Enterprise_Alerts boundary. It monitors system memory utilization and triggers a state transition (Pending -> Firing) within 60 seconds if memory allocation breaches the $50\%$ threshold.

## 🚫 Adım 2: Gereksiz Dosyaları Engellemek (`.gitignore`)

Prometheus ve Grafana'nın yerelde ürettiği veri klasörlerinin GitHub'a yüklenip depoyu kirletmesini engellememiz gerekir. Proje klasöründe `.gitignore` isimli bir dosya aç ve içine şunları yaz:
```text
# Data directories
prometheus_data/
grafana_data/

# OS metadata
.DS_Store
Thumbs.db  
```

