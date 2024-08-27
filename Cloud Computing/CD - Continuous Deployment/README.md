# Continuous Deployment (CD)

This is a process of triggering automatic deployment to the various environments and trigger the automated testing.



### Detailed comparision of Continuous Deployment (CD) services

| Feature/Service            | AWS CodeDeploy                             | Azure Pipelines                        | Google Cloud Deploy                     | GitHub Actions                          | GitLab CI/CD                            |
|----------------------------|--------------------------------------------|----------------------------------------|-----------------------------------------|-----------------------------------------|-----------------------------------------|
| **Supported Platforms**    | EC2, Lambda, ECS, On-Premises              | Azure Services, VMs, Containers, etc.  | Google Cloud Services, GKE, Anthos      | GitHub Repositories, VMs, Containers    | GitLab Repositories, VMs, Containers    |
| **Ease of Integration**    | Seamless with AWS services                 | Seamless with Azure services           | Seamless with Google Cloud services     | Seamless with GitHub Repositories       | Seamless with GitLab Repositories       |
| **Pipeline Configuration** | CodePipeline for orchestration             | YAML-based pipelines                   | YAML-based pipelines                    | YAML-based workflows                    | YAML-based pipelines                    |
| **Rollback Capabilities**  | Automatic rollback, manual triggers        | Manual and automatic rollback          | Automated rollback via Skaffold         | Manual and automated rollback           | Manual and automated rollback           |
| **Deployment Targets**     | EC2, Lambda, ECS, S3, etc.                 | VMs, App Services, Kubernetes, etc.    | GKE, Anthos, Cloud Run                 | VMs, Containers, Serverless functions   | VMs, Containers, Kubernetes, etc.       |
| **Multi-Cloud Support**    | Limited to AWS services                    | Azure services with some multi-cloud   | Limited to Google Cloud services        | Multi-cloud (AWS, Azure, GCP, etc.)     | Multi-cloud with Kubernetes support     |
| **Integration with CI**    | Integrated with AWS CodeBuild              | Integrated with Azure DevOps           | Integrated with Cloud Build             | Integrated with GitHub Actions          | Integrated with GitLab CI/CD            |
| **Monitoring & Alerts**    | CloudWatch, SNS                            | Azure Monitor, Application Insights    | Stackdriver Monitoring                  | GitHub Alerts                           | GitLab Alerts                           |
| **Security Features**      | IAM roles, policies                        | Azure Active Directory, Role-based     | IAM roles, policies, Cloud Identity     | GitHub Secrets, IAM policies            | Role-based access, Secret management    |
| **Pricing**                | Pay-as-you-go, based on usage              | Pay-as-you-go, free tier available     | Pay-as-you-go, free tier available      | Free for public repos, pricing for private | Free tier, pay-as-you-go for advanced features |
| **Scalability**            | High, integrates with AWS Auto Scaling     | High, integrates with Azure Auto Scale | High, integrates with Google Auto Scaling | High, integrates with GitHub-hosted runners | High, integrates with Kubernetes and Auto Scaling |
| **Community & Ecosystem**  | Large AWS community and ecosystem          | Large Azure community and ecosystem    | Growing Google Cloud community          | Large open-source community             | Large open-source and GitLab community  |
| **Use Cases**              | Best for AWS-centric workloads             | Best for Azure-centric workloads       | Best for Google Cloud-centric workloads | Ideal for open-source and multi-cloud   | Ideal for DevSecOps, GitOps workflows   |
| **Learning Curve**         | Moderate, especially if familiar with AWS  | Moderate, especially if familiar with Azure | Moderate, especially if familiar with GCP | Moderate, easy for GitHub users         | Moderate, especially if familiar with GitLab |
