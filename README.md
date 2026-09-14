# Innovatech Solutions - 3 Tier Hybrid Infrastructure Platform (CS1-MA-NCA)

Automated IaC, CI/CD, and Observability stack designed for Innovatech Solutions.

## Tech Stack
* **IaC & Virtualization:** Vagrant, VMware Workstation, Ansible
* **CI/CD:** Self hosted GitHub Actions Runner
* **Observability:** Prometheus, Grafana, Node Exporter (Docker Compose)
* **Application Services:** Nginx Web Server, MySQL Database

## Network Architecture
* **Subnet:** `10.0.2.0/24`
* **app01 (10.0.2.11):** Control Node / CI/CD Runner / Grafana / Prometheus
* **app02 (10.0.2.12):** Nginx Web Server
* **db01 (10.0.2.10):** Isolated MySQL Database (UFW restricted to `10.0.2.12`)

## Quickstart
1. **Clone Repository:**
   ```bash
   git clone [https://github.com/finnluijpers/CS1-MA-NCA-Lab.git](https://github.com/finnluijpers/CS1-MA-NCA-Lab.git)
   cd CS1-MA-NCA-Lab
