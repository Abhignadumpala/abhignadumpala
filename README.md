# Hi, I'm Abhigna 👋

### 🚀 About Me

- ☁️ Cloud & DevOps engineer building production-style infrastructure — on **AWS** and on my own **bare-metal Kubernetes homelab**.
- 🏗️ Deployed an **EKS cluster** on AWS along with hands-on projects across **S3, Lambda, IAM (roles & policies), EC2, VPC**.
- 🖥️ Also built a self-hosted **3-node Kubernetes cluster** (Proxmox, bare-metal) running a full production-style stack end to end.
- 🔁 Automated everything I build with **CI/CD** — GitHub Actions, Jenkins — from test → build → deploy.
- 🧱 Managing infrastructure as code with **Terraform**, and configuration with **Ansible**.
- 📊 Monitoring & observability with **Grafana, Prometheus, and Loki** — used them to catch and fix real production-style bugs.
- 📝 Documenting the build process (and every bug I broke and fixed) on my blog: **Docker & Kubernetes in Action**.
- 🎯 Currently working toward AWS SAA-C03 → HashiCorp Terraform Associate → CKA.
- 🌱 6 years in IT, based in Portugal, looking for **project-based Cloud & DevOps roles**.

---

### 🛠️ Tech Stack

**Cloud**
`AWS` `EKS` `EC2` `S3` `Lambda` `IAM` `VPC` `Proxmox`

**Containers & Orchestration**
`Docker` `Kubernetes`

**Infrastructure as Code & Automation**
`Terraform` `Ansible`

**CI/CD**
`GitHub Actions` `Jenkins` `Self-hosted Runners`

**Monitoring & Observability**
`Grafana` `Prometheus` `Loki`

**Languages & Tools**
`Python` `FastAPI` `PostgreSQL` `Git` `Linux`

**Prior Identity/IAM background**
`Azure Active Directory` `Azure AD Connect` `RBAC` `Conditional Access`

---

### ☁️ AWS Projects

Hands-on projects covering core AWS services:

- **EKS** — deployed and managed a Kubernetes cluster on AWS
- **S3** — static website hosting, bucket policies
- **Lambda** — event-driven functions, S3-triggered pipelines
- **IAM** — custom roles, policies, and permission boundaries
- **EC2 & VPC** — networking, subnets, security groups
- **Terraform** — infrastructure as code for AWS resources
- **Jenkins & GitHub Actions** — CI/CD pipelines for AWS deployments

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

### 🧪 Hands-On Experience

I build and document real Cloud & DevOps projects rather than just following tutorials — using:

- AWS Management Console
- AWS CLI
- Terraform
- Kubernetes (`kubectl`, `kubeadm`)
- GitHub Actions & Jenkins
- Docker

**Hands-on activities included:**
- Deploying and managing an **EKS cluster** on AWS
- Building a self-hosted **3-node Kubernetes cluster** from bare metal (Proxmox, `kubeadm`, Flannel CNI)
- Designing and running a full **CI/CD pipeline** (GitHub Actions, self-hosted runner, Docker Hub)
- Hosting static websites with **S3** and configuring bucket policies
- Building event-driven functions with **Lambda**
- Configuring **VPC** networking — subnets, route tables, security groups
- Managing **IAM** users, roles, and policies
- Setting up centralized **monitoring & observability** (Grafana, Prometheus, Loki)
- Debugging real production-style incidents — DNS crashes, rollout timeouts, misconfigured readiness probes, storage provisioning on bare metal

I continue expanding these skills by building and documenting cloud projects in public GitHub repositories, and writing up what I learn (and break) along the way.

---

### ✅ Recently Completed

- **Terraform** — AWS infrastructure as code
- **CKA preparation** — killer.sh mock exams
- **Deeper AWS** — IAM policies/roles/STS, VPC, EC2, S3, Lambda, CloudFormation

---

### 💼 Open To

`AWS Cloud Engineer` · `DevOps Engineer` · `Cloud Infrastructure Engineer` · `Platform Engineer`

---

### 🤝 Let's Connect

📝 Blog: [mydevopsplaybook.hashnode.dev](https://mydevopsplaybook.hashnode.dev)
🐙 GitHub: [@Abhignadumpala](https://github.com/Abhignadumpala)
