# 🚀 Cloud Architect & DevOps Engineer Roadmap (0 to 2-Yr Experience)

---

## 📌 Phase 1: Linux, Networking & Version Control Fundamentals
- [ ] **1. Linux Core Administration**
  - [ ] Understand user & file permissions (`chmod`, `chown`, `umask`)
  - [ ] Manage background services and daemons using `systemctl` / `journalctl`
  - [ ] Process monitoring and debugging (`ps`, `top`, `htop`, `kill`, `lsof`)
  - [ ] Package management (`apt` / `dnf`) and storage inspection (`df`, `du`)
- [ ] **2. Networking Foundations**
  - [ ] OSI Model layers & TCP vs. UDP traffic
  - [ ] IP addressing, subnets, and CIDR notation (`/24`, `/16`, `/32`)
  - [ ] DNS resolution flow (A records, CNAME, NS, TTL)
  - [ ] SSH key-pair generation (`ssh-keygen`), config files, and `authorized_keys`
- [ ] **3. Git Fundamentals**
  - [ ] Branching strategies (feature branches, `main`, releases)
  - [ ] Merge vs. Rebase workflows and resolving merge conflicts
  - [ ] Writing clear commit messages and maintaining `.gitignore`
- [ ] **🎯 Milestone Project 1:**
  - Spin up a free Linux VM on GCP. Configure passwordless SSH with an SSH key. Harden the instance by disabling root SSH login, enabling a UFW firewall, and configuring an Nginx reverse proxy.

---

## 📌 Phase 2: GCP Enterprise Infrastructure Foundations
- [ ] **1. VPC Networking**
  - [ ] Default VPC vs. Custom VPC architecture
  - [ ] Public subnets vs. Private subnets (no external public IPs)
  - [ ] Ingress/Egress Firewall rules and network tags
  - [ ] Cloud NAT and Cloud Router (outbound internet access for private VMs)
- [ ] **2. Identity & Access Management (IAM)**
  - [ ] Principle of Least Privilege
  - [ ] Google-managed vs. Custom IAM roles
  - [ ] Dedicated Service Accounts (disabling default Compute Engine service account)
- [ ] **3. Core Compute & Storage**
  - [ ] Compute Engine: Instance templates & Managed Instance Groups (MIGs)
  - [ ] Cloud Storage: Storage classes, object versioning, lifecycle rules
  - [ ] Cloud SQL: Private IP provisioning and VPC Peering
- [ ] **🎯 Milestone Project 2:**
  - Build a secure 2-tier environment: A private backend VM communicating with a private Cloud SQL instance, exposed via an External Application Load Balancer.

---

## 📌 Phase 3: Infrastructure as Code (IaC) with Terraform
- [ ] **1. Terraform Core Syntax**
  - [ ] Providers, Resources, Variables, and Outputs
  - [ ] Data sources and resource dependencies (`depends_on`)
  - [ ] Execution lifecycle: `init`, `plan`, `apply`, `destroy`
- [ ] **2. Production State Management**
  - [ ] Remote backend storage using Google Cloud Storage (GCS)
  - [ ] State locking to prevent race conditions
  - [ ] Inspecting state (`terraform state list`, `terraform show`)
- [ ] **3. Modularization & Environments**
  - [ ] Structuring reusable modules (VPC, Compute, Database)
  - [ ] Managing `dev`, `staging`, and `prod` with workspaces/directories
  - [ ] Linting and security scans (`tflint`, `tfsec` / `checkov`)
- [ ] **🎯 Milestone Project 3:**
  - Destroy your manual Phase 2 architecture. Re-provision the entire setup (VPC, Subnets, NAT, and VMs) purely using modular Terraform code.

---

## 📌 Phase 4: Containerization & Kubernetes (GKE)
- [ ] **1. Docker & Container Security**
  - [ ] Writing optimized, multi-stage `Dockerfiles` (<50MB distroless images)
  - [ ] Container isolation: running processes as non-root users
  - [ ] Pushing and scanning images in Google Artifact Registry
- [ ] **2. Kubernetes Core Objects**
  - [ ] Pods, Deployments, and StatefulSets
  - [ ] ConfigMaps and Secrets (externalizing configuration)
  - [ ] Services (`ClusterIP`, `NodePort`, `LoadBalancer`) and GKE Ingress
  - [ ] Storage: PersistentVolumes (PV) and PersistentVolumeClaims (PVC)
- [ ] **3. Cluster Reliability**
  - [ ] Liveness, Readiness, and Startup Probes
  - [ ] Horizontal Pod Autoscaler (HPA) based on CPU/Memory load
  - [ ] Node auto-provisioning & Cluster Autoscaler
- [ ] **🎯 Milestone Project 4:**
  - Containerize a multi-tier web application. Deploy it on a private GKE cluster with an Ingress controller, managed TLS, and auto-scaling.

---

## 📌 Phase 5: CI/CD & GitOps Automation
- [ ] **1. Continuous Integration (CI)**
  - [ ] Automated triggers on Git push and Pull Requests (GitHub Actions)
  - [ ] Automated linting and unit testing stages
  - [ ] Container vulnerability scans (e.g., Trivy)
  - [ ] Building and publishing container tags to Artifact Registry
- [ ] **2. Continuous Delivery (CD) with GitOps**
  - [ ] Understanding Git as the single source of truth
  - [ ] Installing and configuring ArgoCD inside GKE
  - [ ] Packaging Kubernetes resources using Helm Charts
  - [ ] Zero-downtime rolling deployments and automated rollbacks
- [ ] **🎯 Milestone Project 5:**
  - Create a GitOps pipeline: Merging code into your app repo triggers GitHub Actions to build/push an image, and ArgoCD automatically syncs and deploys the update to GKE.

---

## 📌 Phase 6: Observability, SRE & FinOps
- [ ] **1. Cloud Monitoring & Alerting**
  - [ ] Metrics Explorer and custom dashboards in GCP
  - [ ] Log aggregation, filtering, and export in Cloud Logging
  - [ ] Setting up alerting policies for HTTP 5xx error rates and latency
- [ ] **2. Cloud-Native Observability**
  - [ ] Deploying Prometheus to scrape cluster and pod metrics
  - [ ] Creating production monitoring dashboards in Grafana
- [ ] **3. Security & Cloud Armor**
  - [ ] Google Cloud Armor for WAF protection and DDoS mitigation
  - [ ] Secret Manager integration for dynamic secrets injection
- [ ] **4. FinOps & Cost Optimization**
  - [ ] Spot VMs for dev/test workloads
  - [ ] GCS lifecycle policies for archiving cold data
  - [ ] Automated shutdown schedules for non-production environments
- [ ] **🎯 Capstone Project:**
  - Deploy Prometheus/Grafana on GKE, simulate traffic/failure spikes, and verify that alerts trigger notifications automatically while Cloud Armor blocks abusive requests.
