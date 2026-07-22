<div align="center">

  <h1>🛒 Retail Store Microservices Platform</h1>
  <p><b>Production-Grade Cloud-Native Enterprise Architecture on AWS EKS</b></p>

  <br />

  <!-- 3 Fully Clickable Large Cards -->
 <table border="0" style="border-collapse: separate; border-spacing: 12px; width: 100%;">
    <tr>
      <td align="center" width="33%" style="border: 1px solid #30363d; border-radius: 10px; background-color: #0d1117; padding: 20px;">
        <a href="https://github.com/mohamedsameh2002/retail-store-microservices" style="text-decoration: none; color: inherit; display: block;">
          <img src="https://cdn.simpleicons.org/githubactions/2088FF" width="50" height="50" alt="CI/CD Pipeline" />
          <h3 style="margin-top: 12px; color: #58a6ff;">🚀 Application & CI/CD</h3>
        </a>
        <p style="font-family: monospace; color: #e6edf3; margin-top: 5px;">retail-store-microservices</p>
        <p style="font-size: 12px; color: #8b949e; margin-top: 8px;">Microservices Source Code, Dockerfiles & CI/CD Workflows</p>
        <a href="https://github.com/mohamedsameh2002/retail-store-microservices" style="text-decoration: none;">
          <span style="font-size: 11px; color: #2f81f7; font-weight: bold; display: inline-block; margin-top: 6px;">👉 Click to visit repository</span>
        </a>
      </td>
      <td align="center" width="33%" style="border: 1px solid #30363d; border-radius: 10px; background-color: #0d1117; padding: 20px;">
        <a href="https://github.com/mohamedsameh2002/kubernetes-helm-retail-store" style="text-decoration: none; color: inherit; display: block;">
          <img src="https://cdn.simpleicons.org/kubernetes/326CE5" width="50" height="50" alt="Kubernetes Repo" />
          <h3 style="margin-top: 12px; color: #58a6ff;">☸️ K8s & Helm Manifests</h3>
        </a>
        <p style="font-family: monospace; color: #e6edf3; margin-top: 5px;">kubernetes-helm-retail-store</p>
        <p style="font-size: 12px; color: #8b949e; margin-top: 8px;">Helm Charts, Ingress Controllers, Secrets & ExternalDNS</p>
        <a href="https://github.com/mohamedsameh2002/kubernetes-helm-retail-store" style="text-decoration: none;">
          <span style="font-size: 11px; color: #2f81f7; font-weight: bold; display: inline-block; margin-top: 6px;">👉 Click to visit repository</span>
        </a>
      </td>
      <td align="center" width="33%" style="border: 1px solid #30363d; border-radius: 10px; background-color: #0d1117; padding: 20px;">
        <a href="https://github.com/mohamedsameh2002/terraform-retail-store" style="text-decoration: none; color: inherit; display: block;">
          <img src="https://cdn.simpleicons.org/terraform/844FBA" width="50" height="50" alt="Terraform Repo" />
          <h3 style="margin-top: 12px; color: #58a6ff;">🏗️ Infrastructure as Code</h3>
        </a>
        <p style="font-family: monospace; color: #e6edf3; margin-top: 5px;">terraform-retail-store</p>
        <p style="font-size: 12px; color: #8b949e; margin-top: 8px;">AWS VPC, EKS Cluster, Karpenter & Modular IaC Setup</p>
        <a href="https://github.com/mohamedsameh2002/terraform-retail-store" style="text-decoration: none;">
          <span style="font-size: 11px; color: #2f81f7; font-weight: bold; display: inline-block; margin-top: 6px;">👉 Click to visit repository</span>
        </a>
      </td>
    </tr>
  </table>

</div>

---

## 📐 System Architecture & Platform Overview

The platform consists of **5 polyglot microservices** built with Java Spring Boot, GoLang, and Node.js. The infrastructure is engineered for production workloads on AWS EKS, featuring complete data isolation and native integration with the AWS Data Plane services.

<br />

<div align="center">
  <img src="https://placehold.co/1200x500/1e293b/00f2fe?text=1.+Full+Microservices+%26+AWS+Data+Plane+Architecture" alt="Architecture Diagram" width="100%" />
  <p><i>Figure 1: End-to-End Microservices Architecture with AWS RDS, DynamoDB, ElastiCache, and SQS Integration</i></p>
</div>

---

## 📦 Containerization & Docker Build Optimization

All applications are containerized using production security best practices. Leveraging **Docker BuildKit** and **Multi-Stage Builds**, image footprints are optimized to reduce security vulnerabilities. The images support multi-platform architectures (`AMD64` & `ARM64`) with layer caching, health checks, and strict non-root user execution.

<br />

<div align="center">
  <img src="https://placehold.co/1200x450/0f172a/38bdf8?text=2.+Docker+BuildKit+%26+Multi-Stage+Container+Pipeline" alt="Docker Pipeline" width="100%" />
  <p><i>Figure 2: Multi-Stage Docker Build Optimization & Multi-Platform Registry Flow</i></p>
</div>

---

## 🏗️ Infrastructure as Code with Terraform

The cloud platform is fully automated using reusable **Terraform Modules**. It provisions a highly resilient AWS VPC architecture with public/private subnets and manages remote state locking via Amazon S3 and DynamoDB. The EKS cluster includes IAM OIDC provider integration for granular pod-level security permissions (IRSA).

<br />

<div align="center">
  <img src="https://placehold.co/1200x450/1e293b/a855f7?text=3.+AWS+VPC+%26+EKS+Cluster+Provisioning+with+Terraform" alt="Terraform AWS Infrastructure" width="100%" />
  <p><i>Figure 3: Automated AWS Infrastructure Topology Provisioned via Modular Terraform</i></p>
</div>

---

## 🔐 Zero-Trust Secrets Management & Storage Persistence

To enforce a zero-trust architecture, sensitive credentials are never stored in source code. Using the **Secrets Store CSI Driver** and **AWS Secrets Manager Driver**, secrets are dynamically mounted directly into application pods. Persistent workloads utilize the **AWS EBS CSI Driver** for dynamic storage provisioning via Kubernetes StorageClasses.

<br />

<div align="center">
  <img src="https://placehold.co/1200x450/0f172a/f43f5e?text=4.+Kubernetes+Secrets+Store+CSI+%26+EBS+Dynamic+Storage" alt="Secrets & Storage Flow" width="100%" />
  <p><i>Figure 4: Secure AWS Secrets CSI Mounting & EBS Dynamic Volume Provisioning Lifecycle</i></p>
</div>

---

## 🌐 Dynamic Traffic Routing, TLS & Automated DNS

Inbound traffic is routed dynamically through the **AWS Load Balancer Controller**, which automatically provisions Application Load Balancers (ALB) based on Kubernetes Ingress objects. SSL/TLS termination is managed seamlessly via **AWS Certificate Manager (ACM)**, while **ExternalDNS** automatically synchronizes domain records directly with **Amazon Route53**.

<br />

<div align="center">
  <img src="https://placehold.co/1200x450/1e293b/38bdf8?text=5.+Ingress+ALB+Controller+%2B+Route53+ExternalDNS" alt="Ingress & DNS Setup" width="100%" />
  <p><i>Figure 5: Automated Route53 DNS Sync and AWS ALB SSL Termination Flow</i></p>
</div>

---

## ⚡ Smart Autoscaling with Karpenter & Horizontal Pod Autoscaler (HPA)

To optimize compute costs by up to **70%**, the platform uses **Karpenter** for rapid, pod-driven node provisioning. It employs a diversified **Spot Instances** strategy with automated interruption handling via `EventBridge → SQS → Karpenter` for zero-downtime pod evictions. HPA dynamically scales pod replicas while Karpenter right-sizes underlying nodes in real time.

<br />

<div align="center">
  <img src="https://placehold.co/1200x450/0f172a/34d399?text=6.+Karpenter+Spot+Autoscaling+%26+Interruption+Handling" alt="Autoscaling Architecture" width="100%" />
  <p><i>Figure 6: Karpenter Spot Interruption Workflow with HPA Integration</i></p>
</div>

---

## 📊 Full-Stack Observability with OpenTelemetry

Complete system observability is provided by the **AWS Distro for OpenTelemetry (ADOT)**. Distributed tracing is exported to **AWS X-Ray** with custom health-check filtering (saving up to 85% in tracing overhead). Log aggregation is handled by **CloudWatch Insights**, while system metrics are monitored via **Amazon Managed Prometheus** and **Grafana**.

<br />

<div align="center">
  <img src="https://placehold.co/1200x450/1e293b/f59e0b?text=7.+OpenTelemetry+Traces+(X-Ray)+%26+Prometheus/Grafana" alt="Observability Architecture" width="100%" />
  <p><i>Figure 7: Unified Observability Pipeline with OpenTelemetry, X-Ray, and Grafana Dashboards</i></p>
</div>

---

## 🔄 GitOps Automated CI/CD Pipeline

Application deployments strictly follow **GitOps** principles:
1. Developers commit code changes to **GitHub**.
2. **GitHub Actions** runs CI workflows, using keyless AWS OIDC authentication to build and push tagged images to **AWS ECR**.
3. Helm values are updated with new image tags.
4. **ArgoCD** detects the configuration drift, synchronizes the Kubernetes cluster automatically, and enables instant zero-downtime rollbacks if required.

<br />

<div align="center">
  <img src="https://placehold.co/1200x450/0f172a/6366f1?text=8.+GitHub+Actions+CI+%2B+ArgoCD+GitOps+Continuous+Deployment" alt="CI/CD Pipeline Architecture" width="100%" />
  <p><i>Figure 8: End-to-End Automated CI/CD Engine via GitHub Actions and ArgoCD GitOps</i></p>
</div>

---

<div align="center">
  <br />
  <p>Designed & Developed by <b>Mohammed Sameh</b> | DevOps & Platform Engineer</p>
</div>
