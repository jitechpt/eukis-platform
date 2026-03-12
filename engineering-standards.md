# trasaki Engineering Standards

This document defines the engineering standards used in the trasaki platform, a product developed by Jitech.

The goal of these standards is to ensure:

- Consistency across services
- High engineering quality
- Scalable cloud-native architecture
- Secure software delivery
- Maintainable and observable systems

These standards will evolve as the platform grows.

---

# 1. Engineering Principles

The trasaki platform follows these engineering principles:

• Cloud-native architecture  
• Infrastructure as Code  
• Automation-first operations  
• Secure by design  
• Observability-first systems  
• Continuous delivery  
• Documentation as code  

All systems must be designed to be reproducible, automated, and observable.

---

# 2. Repository Strategy

The trasaki platform uses a **multi-repository strategy**.

Each major component lives in its own repository.

Example structure:

Frontend

trasaki-frontend


Backend services


trasaki-catalog-service
trasaki-user-service
trasaki-listing-service
trasaki-search-service


Infrastructure


trasaki-infra-modules
trasaki-infra-live


Platform engineering


trasaki-platform


Architecture documentation


trasaki-architecture


---

# 3. Repository Naming Convention

All repositories follow this pattern:


trasaki-<component>


Examples:


trasaki-frontend
trasaki-catalog-service
trasaki-user-service
trasaki-platform
trasaki-architecture


Infrastructure repositories follow:


trasaki-infra-<scope>


Examples:


trasaki-infra-modules
trasaki-infra-live


---

# 4. Branch Strategy

The project follows a simplified **Git Flow** model.

Main branches:


main
develop


Feature branches:


feature/<name>


Examples:


feature/catalog-service
feature/terraform-modules
feature/github-actions-pipeline


Bug fixes:


fix/<issue>


Example:


fix/login-error


Hotfix branches:


hotfix/<issue>


---

# 5. Pull Request Standards

All changes must be delivered through Pull Requests.

Requirements:

• Description of change  
• Linked issue or task  
• Tests added when applicable  
• Documentation updated if needed  

Pull requests must pass:

- CI pipeline
- linting
- security checks

---

# 6. Commit Message Convention

Commit messages follow this pattern:


type: description


Examples:


feat: add catalog service skeleton
fix: correct authentication issue
docs: update architecture documentation
ci: add GitHub Actions pipeline
refactor: simplify service configuration


Common commit types:


feat
fix
docs
ci
refactor
test
chore


---

# 7. Documentation Standards

Every repository must contain:


README.md
docs/


README must include:

- Project description
- Architecture overview
- Setup instructions
- Development workflow
- Technology stack

Documentation should be written in Markdown.

Future documentation automation tools may include:

- MkDocs
- Backstage TechDocs
- terraform-docs

---

# 8. Infrastructure as Code Standards

Infrastructure must always be defined as code.

Tools used:

Terraform  
Terragrunt  

Repository structure example:


terraform/
modules/
environments/
dev/
staging/
prod/


Terraform modules must be reusable and documented.

---

# 9. Container Standards

All services must run as containers.

Containerization tool:

Docker

Requirements:

• Lightweight images  
• Multi-stage builds  
• Security scanning  
• Minimal base images  

Images will be stored in a container registry.

---

# 10. Kubernetes Standards

The trasaki platform runs on Kubernetes.

Packaging tool:

Helm

Requirements:

• Services must be stateless when possible  
• Configuration via environment variables  
• Health checks required  
• Resource limits defined  

Future platform components:

• Istio (service mesh)  
• Karpenter (node autoscaling)  

---

# 11. CI/CD Standards

Continuous integration and deployment are handled using:

GitHub Actions

Pipelines must include:

• Build  
• Test  
• Static analysis  
• Security scanning  
• Container build  
• Deployment automation  

Deployment strategy will evolve toward GitOps.

Possible tools:

• ArgoCD

---

# 12. Security Standards

Security must be integrated into the development lifecycle.

Tools planned:

SonarQube  
Snyk  
OWASP ZAP  

Security practices include:

• Dependency scanning  
• Container scanning  
• Static code analysis  
• Secure secrets management  

---

# 13. Observability Standards

Systems must be observable from the beginning.

Observability stack:

Prometheus  
Grafana  
Centralized logging  
Distributed tracing (future)

Services must expose metrics and logs.

---

# 14. Architecture Standards

Architecture must follow modern cloud-native patterns.

Guidelines:

• Domain-driven service boundaries  
• API-first design  
• Stateless services when possible  
• Event-driven communication where applicable  

Architecture documentation should follow the **C4 model**.

Levels:

Context  
Container  
Component  
Code

---

# 15. Engineering Culture

Engineering culture is as important as technology.

The trasaki platform values:

• learning in public  
• documentation  
• experimentation  
• continuous improvement  
• automation  
• collaboration  

The platform also serves as a **learning environment for platform engineering and cloud-native system design**.

---

# 16. Future Improvements

These standards will evolve as the platform matures.

Future topics:

• platform engineering golden paths  
• service templates  
• internal developer portal (Backstage)  
• automated documentation  
• platform scorecards  
