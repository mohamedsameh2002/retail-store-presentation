<div align="center">

  <h1>🛒 Retail Store Microservices Platform</h1>
  <p><b>Production-Grade Cloud-Native Enterprise Architecture on AWS EKS</b></p>

  <br />

  <!-- 3 Big Navigation Cards / Icons -->
  <table border="0" style="border-collapse: collapse; width: 100%;">
    <tr>
      <td align="center" width="33%" style="padding: 15px; border: 1px solid #30363d; border-radius: 8px;">
        <a href="https://github.com/mohamedsameh2002/retail-store-microservices">
          <img src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/github-actions/github-actions.png" width="60" alt="Project Repo" />
          <h3 style="margin-top: 10px;">🚀 Main Application</h3>
          <p><code>retail-store-microservices</code></p>
          <sub>Microservices Code, Dockerfiles & CI/CD Pipelines</sub>
        </a>
      </td>
      <td align="center" width="33%" style="padding: 15px; border: 1px solid #30363d; border-radius: 8px;">
        <a href="https://github.com/mohamedsameh2002/kubernetes-helm-retail-store">
          <img src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/kubernetes/kubernetes.png" width="60" alt="Kubernetes Repo" />
          <h3 style="margin-top: 10px;">☸️ K8s & Helm</h3>
          <p><code>kubernetes-helm-retail-store</code></p>
          <sub>Helm Charts, Ingress, Secrets & ExternalDNS</sub>
        </a>
      </td>
      <td align="center" width="33%" style="padding: 15px; border: 1px solid #30363d; border-radius: 8px;">
        <a href="https://github.com/mohamedsameh2002/terraform-retail-store">
          <img src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/terraform/terraform.png" width="60" alt="Terraform Repo" />
          <h3 style="margin-top: 10px;">🏗️ Infrastructure</h3>
          <p><code>terraform-retail-store</code></p>
          <sub>AWS VPC, EKS Cluster, Karpenter & IaC Modules</sub>
        </a>
      </td>
    </tr>
  </table>

</div>

---

## 📐 System Architecture & Overview

تتكون المنصة من **5 خدمات مصغرة (Polyglot Microservices)** تعمل بلغات برمجة مختلفة (Java Spring Boot, Go, Node.js). تم تصميم البنية التحتية بالكامل لتعمل على بيئة إنتاجية جاهزة للعمليات المعقدة على AWS EKS مع فصل كامل للبيانات واستخدام AWS Data Plane المتكامل.

<br />

<div align="center">
  <img src="https://placehold.co/1200x500/1e293b/00f2fe?text=1.+Full+Microservices+%26+AWS+Data+Plane+Architecture" alt="Architecture Diagram" width="100%" />
  <p><i>شكل 1: المخطط المعماري الشامل للخدمات وتكاملها مع قواعد بيانات AWS RDS و DynamoDB و ElastiCache</i></p>
</div>

---

## 📦 Containerization & Build Optimization (Modules 01-05)

تم تعبئة جميع التطبيقات داخل Docker Containers باستخدام أفضل ممارسات الأمان. اعتمدنا على **Docker BuildKit** وتقنية **Multi-Stage Builds** لتصغير حجم الصور وتقليل ثغرات الأمان، بالإضافة إلى دعم منصات متعددة (AMD64 & ARM64) مع تنظيم كامل لترتيب التشغيل واختبارات الصحة (Health Checks).

<br />

<div align="center">
  <img src="https://placehold.co/1200x450/0f172a/38bdf8?text=2.+Docker+BuildKit+%26+Multi-Stage+Container+Pipeline" alt="Docker Pipeline" width="100%" />
  <p><i>شكل 2: مراحل بناء Docker Container المحسّنة وتوزيع Layers للحصول على أقصى سرعة بناء</i></p>
</div>

---

## 🏗️ Infrastructure as Code with Terraform (Modules 06-07)

تدار البنية التحتية بالكامل بواسطة **Terraform Modules** لإنشاء بيئة AWS VPC احترافية مع شبكات عامة وخاصة (Public/Private Subnets)، وحفظ الحالة (Remote State) عبر S3 مع DynamoDB للقفل (State Locking). كما يتم إنشاء مجتمع EKS مع إدارة هويات IAM ودعم OIDC مخصص للتطبيقات.

<br />

<div align="center">
  <img src="https://placehold.co/1200x450/1e293b/a855f7?text=3.+AWS+VPC+%26+EKS+Cluster+Provisioning+with+Terraform" alt="Terraform AWS Infrastructure" width="100%" />
  <p><i>شكل 3: هيكلية الشبكة VPC وعنقود AWS EKS المصممين بواسطة Terraform</i></p>
</div>

---

## 🔐 Zero-Trust Secrets & Persistence (Modules 08-11)

تأمين الأسرار وقواعد البيانات يتم بدون كتابة أي كلمة سر داخل الأكواد! نستخدم **Secrets Store CSI Driver** و **AWS Secrets Manager Driver** لربط الأسرار مباشرة من AWS إلى الـ Pods، مع استخدام **AWS EBS CSI Driver** لإدارة الأقراص المرنة والربط الديناميكي للمساحات التخزينية.

<br />

<div align="center">
  <img src="https://placehold.co/1200x450/0f172a/f43f5e?text=4.+Kubernetes+Secrets+Store+CSI+%26+EBS+Dynamic+Storage" alt="Secrets & Storage Flow" width="100%" />
  <p><i>شكل 4: آلية جلب الأسرار الآمنة ومزامنة التخزين الديناميكي على Kubernetes</i></p>
</div>

---

## 🌐 Dynamic Traffic Ingress & ExternalDNS (Modules 12-16)

يتم توجيه المرور عبر **AWS Load Balancer Controller** لإنشاء Application Load Balancer (ALB) تلقائياً، مع دعم شهادات SSL/TLS المجانية عبر **AWS Certificate Manager (ACM)**. ويقوم إضافية **ExternalDNS** بإنشاء وتسجيل أحدث عناوين DNS في **Amazon Route53** تلقائياً بمجرد إطلاق الخدمة.

<br />

<div align="center">
  <img src="https://placehold.co/1200x450/1e293b/38bdf8?text=5.+Ingress+ALB+Controller+%2B+Route53+ExternalDNS" alt="Ingress & DNS Setup" width="100%" />
  <p><i>شكل 5: مسار حركة المرور من النطاق الخارجي Route53 وحتى التطبيقات عبر Ingress ALB</i></p>
</div>

---

## ⚡ Smart Autoscaling with Karpenter & HPA (Modules 17-18)

لتحقيق أقصى توفير في التكلفة تصل إلى **70%**، اعتمدنا على **Karpenter** لتوسعة الخوادم (Nodes) بناءً على حاجة الـ Pods اللحظية وبدعم كامل لخوادم **Spot Instances**. يتم التعامل مع تنبيهات الانقطاع عبر `EventBridge → SQS → Karpenter` لضمان إعادة توزيع الحمولات بدون أي توقف (Zero-Downtime)، بالدمج مع **HPA** للتوسع الأفقي للـ Pods.

<br />

<div align="center">
  <img src="https://placehold.co/1200x450/0f172a/34d399?text=6.+Karpenter+Spot+Autoscaling+%26+Interruption+Handling" alt="Autoscaling Architecture" width="100%" />
  <p><i>شكل 6: آلية التوسع الذكي مع Karpenter للتقليل المباشر للتكاليف ومعالجة انقطاع الـ Spot</i></p>
</div>

---

## 📊 Full-Stack Observability with OpenTelemetry (Module 20)

تتبع المراقبة الشاملة عبر **AWS Distro for OpenTelemetry (ADOT)** لجمع التتبع (Traces) والتكلفة عبر **AWS X-Ray** (مع تصفية فحص الصحة لتوفير 85% من تكاليف المراقبة). ويتم تجميع السجلات في **CloudWatch Insights** والمقاييس على **Amazon Managed Prometheus & Grafana**.

<br />

<div align="center">
  <img src="https://placehold.co/1200x450/1e293b/f59e0b?text=7.+OpenTelemetry+Traces+(X-Ray)+%26+Prometheus/Grafana" alt="Observability Architecture" width="100%" />
  <p><i>شكل 7: منظومة المراقبة والـ Telemetry المتكاملة عبر X-Ray و Prometheus و Grafana</i></p>
</div>

---

## 🔄 Automated GitOps CI/CD Pipeline (Module 21)

يتم التطوير وفق منهجية **GitOps** المتقدمة:
1. يرفع المطور الكود إلى **GitHub**.
2. تنطلق **GitHub Actions** عبر OIDC بدون مفاتيح أكسس لبناء الصورة ورفعها لـ **AWS ECR**.
3. يتم تحديث ملفات **Helm Values** تلقائياً.
4. يكتشف **ArgoCD** التغيير داخل العنقود ويقوم بتطبيقه وسحب الصور فوراً مع إمكانية الـ Rollback التلقائي.

<br />

<div align="center">
  <img src="https://placehold.co/1200x450/0f172a/6366f1?text=8.+GitHub+Actions+CI+%2B+ArgoCD+GitOps+Continuous+Deployment" alt="CI/CD Pipeline Architecture" width="100%" />
  <p><i>شكل 8: خط الإنتاج التلقائي الكامل بداية من سحب الكود وحتى النشر عبر ArgoCD</i></p>
</div>

---

<div align="center">
  <br />
  <p> Designed & Developed by <b>Mohammed Sameh</b> | DevOps & Platform Engineer</p>
</div>
