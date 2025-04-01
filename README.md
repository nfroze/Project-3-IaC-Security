# ☁️ Project 3: Infrastructure as Code (IaC) Security

## 1. Overview 🚀
This project showcases **secure AWS infrastructure provisioning** with **Terraform**, enforcing **least privilege** IAM policies. It features a **two-step CI/CD pipeline**—one job for **IaC scanning** and another for **deployment**—integrating **Checkov** to detect misconfigurations before anything goes live.

---

## 2. Key Technologies 🛠
- **Terraform** ⚙️  
  - Defines AWS resources in `main.tf` and manages state via a secured S3 backend.
- **AWS** ☁️  
  - Focus on IAM, CloudTrail, GuardDuty, ensuring robust access control and logging.
- **Checkov** 🔎  
  - Scans Terraform code for security misconfigurations before deployment.
- **GitHub Actions** 🤖  
  - Automates scanning and deployment in a two-step pipeline.

---

## 3. Security Highlights 🔒
- **Least Privilege IAM Policies**  
  - Scoped permissions for admins, developers, and DevSecOps roles.
- **Automated IaC Scanning**  
  - Checkov prevents insecure infrastructure from being deployed.
- **Terraform State Management**  
  - Centralized and secured via S3 backend.
- **Separation of Scan & Deploy**  
  - Ensures only validated, secure code is applied.

---

## 4. CI/CD Workflow 🔄
1. **Code Checkout & AWS Credentials**  
   - GitHub Actions pulls the IaC code and configures AWS access from encrypted secrets.
2. **Terraform Init**  
   - Prepares the working directory with required plugins and modules.
3. **Checkov Scan**  
   - Flags insecure configurations using `checkov`.
4. **Plan & Deploy (if safe)**  
   - Runs `terraform plan` and applies changes only if scan passes.

> 🔐 **Note:** Deployment only occurs if scanning passes — enforcing a shift-left security model.

---

## 5. Value for Organizations 💼
- **Auditable Deployments**  
  - Version-controlled and automated — compliant with modern DevOps practices.
- **Reduced Attack Surface**  
  - IAM hardening through principle of least privilege.
- **Misconfiguration Prevention**  
  - Proactive issue detection via Checkov.
- **Repeatable and Scalable**  
  - Infrastructure-as-Code enables consistency across environments.

---

## 6. Conclusion ✅
By combining **Terraform**, **Checkov**, and **GitHub Actions** in a secure, automated workflow, this project highlights how teams can provision **cloud infrastructure safely and at scale**. It reflects real-world practices for enforcing compliance, security, and operational excellence from the start.

---

🔗 [Back to my GitHub Profile](https://github.com/nfroze)