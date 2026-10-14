# Hi, I'm Abhigna 👋

**Cloud & DevOps Engineer** · 6 years in IT · Based in Portugal · Open to project-based Cloud & DevOps roles

---

### 🚀 About Me

- ☁️ Cloud & DevOps engineer with **6 years in IT** and a background in **identity and access management** (Azure AD, RBAC, Conditional Access).
- 🏗️ I design, deploy and operate production-style infrastructure on **AWS** and on a **self-hosted bare-metal Kubernetes** platform.
- 🔁 I automate delivery with **CI/CD** (GitHub Actions, Jenkins), manage infrastructure as code with **Terraform** and configuration with **Ansible**.
- 📊 I run observability with **Prometheus, Grafana and Loki**, and use it to root-cause production-style incidents.
- 📝 I keep my skills current through continuous hands-on builds, and document each one end to end: architecture, setup, and every issue debugged.

---

### 🛠️ Tech Stack

**Cloud:** `AWS` `EKS` `EC2` `VPC` `S3` `Lambda` `IAM` `Route 53` `Proxmox`

**Containers & Orchestration:** `Docker` `Kubernetes` `kubeadm` `Helm`

**Infrastructure as Code & Automation:** `Terraform` `Ansible` `Bash`

**CI/CD:** `GitHub Actions` `Jenkins` `Self-hosted Runners` `Docker Hub`

**Monitoring & Observability:** `Prometheus` `Grafana` `Loki` `Alertmanager`

**Web, Data & Messaging:** `Nginx` `PostgreSQL` `MySQL` `MongoDB` `Redis` `RabbitMQ`

**Languages & Tools:** `Python` `FastAPI` `Git` `Linux (RHEL, Ubuntu)` `systemd`

**Identity & Access:** `Azure Active Directory` `Azure AD Connect` `RBAC` `Conditional Access`

---

### 🏗️ Projects

**1. [RoboShop on AWS — Microservices E-Commerce Deployment](https://github.com/Abhignadumpala/roboshop-aws-microservices)** · *Oct 2026*
An online robot store deployed as **11 services on 11 EC2 instances**, manually by design, as the baseline for automating it.

- 🗄️ MongoDB, Redis, MySQL, RabbitMQ + 6 microservices in 4 languages (Node.js, Java/Spring Boot, Python, Go) + Nginx reverse proxy
- 🌐 Service discovery with **Route 53** private DNS records on my own domain, no hard-coded IPs
- 🔐 11 security groups with least-privilege SG-to-SG rules; every app runs as a non-root `systemd` service
- 🔍 Debugged a Redis connection failure (open-then-closed connection → `protected-mode`) with SG, DNS and port all healthy
- 📦 Resilience test: stopped the dispatch service mid-order; the order waited in RabbitMQ and was processed on recovery, **zero orders lost**

**2. [3-Tier DevOps Platform on Bare-Metal Kubernetes](https://github.com/Abhignadumpala/task-tracker-3tier-devops)** · *Jul–Aug 2026* · ✅ Completed
React → FastAPI → PostgreSQL, deployed to a self-hosted Kubernetes cluster, from scratch, on real hardware, not managed cloud K8s.

- 🖥️ 3-node cluster (1 master, 2 workers) on a Dell OptiPlex 7050 Micro via Proxmox, bootstrapped with `kubeadm` + Flannel CNI
- 🔄 Full CI/CD: GitHub Actions (pytest against a Postgres service) → Docker Hub → automated rollout through a self-hosted runner inside the homelab
- 📦 `local-path-provisioner` for bare-metal storage (no cloud StorageClass out of the box)
- 🔐 Only the frontend exposed (NodePort); backend and Postgres internal (ClusterIP); non-root containers, probes, resource limits, 2 backend replicas
- 📈 Loki + Grafana (Helm) for centralized logs — caught a hidden Postgres readiness-probe bug (`pg_isready` without `-d`) that `kubectl get pods` showed as healthy
- 📚 Debugging documented end to end: kubeadm token expiry, rollout timeouts, CI path issues, probe misconfiguration
- 🧭 Planned next: Ingress-nginx, MetalLB, HA control plane, Argo CD (GitOps), Prometheus metrics, HPA

**3. [Secure DevSecOps Pipeline & Monitoring](https://github.com/Abhignadumpala/devops-interview-prep)** · *Oct 2026*
- 🔄 GitHub Actions: lint → test → build → deploy, matrix tests (2 OS × 3 Node versions, parallel: **32 s vs 120 s** sequential), npm caching, CodeQL SAST, Dependabot, required status checks
- 🧩 Composite actions and reusable workflows; self-hosted runner on EC2
- 📈 Prometheus + Grafana + Node Exporter, EC2 service discovery via IAM role, Alertmanager CPU alert fired under load

**4. [DevOps Notes](https://github.com/Abhignadumpala/devops-notes)** — day-by-day fundamentals: Linux, Nginx reverse proxy & load balancing, DNS on my own domain (Route 53), 3-tier deployments, databases and message queues

📝 **Blog:** [Docker & Kubernetes in Action](https://mydevopsplaybook.hashnode.dev)

---

### ⚙️ Core Capabilities

| Area | What I do |
|------|-----------|
| **AWS** | EKS, EC2, VPC (subnets, route tables, security groups), S3 (static hosting, bucket policies), Lambda (event-driven, S3-triggered), IAM (roles, policies, permission boundaries), Route 53 |
| **Kubernetes** | Bare-metal clusters with kubeadm, EKS, Deployments vs StatefulSets, storage provisioning, probes, Services and exposure |
| **CI/CD** | Test → build → deploy pipelines, matrix builds, caching, reusable workflows, self-hosted runners, image registries |
| **IaC & Configuration** | Terraform for AWS resources, Ansible for server configuration |
| **Observability** | Metrics, centralized logs, dashboards, alerting, EC2 service discovery |
| **Security** | Least-privilege IAM and security groups, SAST (CodeQL), dependency updates (Dependabot), non-root containers, secrets kept out of Git |
| **Troubleshooting** | DNS, service-to-service connectivity, rollout timeouts, readiness probes, storage on bare metal, layer-by-layer root cause analysis |

---

### 📝 Blog & Writing

**AWS Deep Dive**
- [Understanding Amazon EBS (Elastic Block Store) — Simple Guide](https://aws-deep-dive.hashnode.dev/understanding-amazon-ebs-elastic-block-store-simple-guide)
- [Boost EC2 Storage: Create and Attach EBS Volumes (Step by Step)](https://aws-deep-dive.hashnode.dev/boost-ec2-storage-create-and-attach-ebs-volumes-step-by-step)

**Kubernetes**
- [Understanding Kubernetes Architecture (LinkedIn)](https://www.linkedin.com/posts/dumpala-abhigna-bbba022a5_understanding-kubernetes-architecture-share-7448454485183647744-HMIA/)
- [Kubernetes StatefulSets vs Deployments — Theory Overview](https://kubernetes-statefulset-vs-deployment.hashnode.dev/understanding-kubernetes-statefulsets-and-how-they-differ-from-deployments-theory-overview)
- [Kubernetes Hands-On: Deployment vs StatefulSet on Amazon EKS](https://understanding-kubernetes-statefulset.hashnode.dev/kubernetes-hands-on-project-deployment-vs-statefulset-on-amazon-eks)
- [ImagePullBackOff Explained: Troubleshooting Kubernetes Image Pull Errors](https://troubleshootingk8s.hashnode.dev/imagepullbackoff-explained-troubleshoot-kubernetes-image-pull-errors)

**3-Tier DevOps Platform Series**
- [Part 1 — Docker, DevOps & Kubernetes (LinkedIn)](https://www.linkedin.com/posts/dumpala-abhigna-bbba022a5_docker-devops-kubernetes-ugcPost-7483625564734484481-Zxv9/)


---

### 🌱 Currently

- Building and documenting hands-on projects end to end in public repos, with a focus on **automating** the deployments I have built manually

---

### 💼 Open To

`AWS Cloud Engineer` · `DevOps Engineer` · `Cloud Infrastructure Engineer` · `Platform Engineer`

---

### 🤝 Let's Connect

📝 Blog: [mydevopsplaybook.hashnode.dev](https://mydevopsplaybook.hashnode.dev)
🐙 GitHub: [@Abhignadumpala](https://github.com/Abhignadumpala)
