# Innovatech Solutions (CS1-MA-NCA)

Automated IaC, CI/CD, and Observability stack designed for Innovatech Solutions.

## Tech Stack

* **IaC & virtualization:** Vagrant, VMware Workstation, Terraform (AWS VPC), Ansible
* **CI/CD:** Self-hosted GitHub Actions Runner (hosted on `app01`)
* **Observability:** Prometheus, Grafana, Node Exporter (Docker Compose)
* **Application Services:** Nginx Web Server, MySQL Database

## Network Architecture

* **On-Premise Private Subnet:** `10.0.2.0/24` (VMware / Vagrant)
  * `app01` (`10.0.2.11`): Control Node / CI/CD Runner / Grafana / Prometheus
  * `app02` (`10.0.2.12`): Nginx Web Server
  * `db01` (`10.0.2.10`): Isolated MySQL Database (UFW restricted to `10.0.2.12`)
* **AWS Cloud Bursting VPC:** `10.1.0.0/16` (Terraform)
  * **Public Subnet:** `10.1.1.0/24`
  * `aws_app01` (`10.1.1.8` / Public IP): Cloud Bursting Nginx Node & Node Exporter

## Quickstart

1. **Clone Repository:**
   ```bash
   git clone [https://github.com/finnluijpers/CS1-MA-NCA-Lab.git](https://github.com/finnluijpers/CS1-MA-NCA-Lab.git)
   cd CS1-MA-NCA-Lab
