# CD - Continuous Deployment-Best Practices

This is a process that ensures the changes are automatically built, tested and deployed to production in regular intervals,

This process helps in

- Minimize manual intervention
- Speedup the process

## Key things

- Automated Testing : Automated testing will save lot of time and reduce errors
- Rollback mechanism : In case of any unlikely event, the process is set to revert the changes made to the system, ensuring the robustness of the application.

## **CD Workflow:**

- Code Commit:
- Automated Build :
- Automated testing :
- Automated packaging :
- Deploy to staging :
- Pre-prodution verification :
- Automated deployment to production :
- Post deployment monitoring :

## Popular CD Tools:

- Azure DevOps 
- GitHub Actions
- AWS CodePipeline
- Jenkins
- GitLab CI/CD

## Comparison of Popular CD Tools:

Comparison table of popular Continuous Deployment (CD) tools available for AWS, Azure, and Google Cloud Platform (GCP):

| **Feature/Aspect**     | **AWS CodePipeline**             | **Azure DevOps (Pipelines)**          | **Google Cloud Build**             |
|------------------------|----------------------------------|---------------------------------------|------------------------------------|
| **Platform**           | AWS                              | Azure                                | Google Cloud                      |
| **Integration**        | Native integration with AWS services (EC2, S3, Lambda) | Native integration with Azure services (VMs, App Services) | Native integration with GCP services (GCE, GKE, Cloud Functions) |
| **Supported Languages**| Supports all major languages (Java, Python, Node.js, .NET, etc.) | Supports all major languages (.NET, Java, Python, Node.js, etc.) | Supports all major languages (Java, Python, Node.js, Go, etc.)  |
| **Customizability**    | Highly customizable with AWS Lambda, custom scripts | Highly customizable with YAML pipelines, custom scripts | Customizable using build config files, custom scripts             |
| **Pipeline Orchestration** | Visual editor for creating multi-step CI/CD pipelines | YAML-based pipelines with GUI support for simple builds | YAML-based configuration files for flexible pipeline setup      |
| **Security**           | Integration with IAM roles, encrypted artifacts, and logs | Integration with Azure Active Directory, secure variables | Integration with IAM, encryption of build artifacts, audit logging |
| **Scalability**        | Highly scalable with auto-scaling using EC2 instances and Lambda | Scalable with Azure DevOps Services, hosted agents, and private agents | Scales automatically with GCP infrastructure                    |
| **Monitoring & Logging** | CloudWatch integration for logging and monitoring | Built-in monitoring, integration with Azure Monitor, Application Insights | Stackdriver (now Cloud Monitoring) integration                  |
| **Source Control**     | Integration with AWS CodeCommit, GitHub, Bitbucket | Built-in Azure Repos, GitHub, Bitbucket integration | Integration with Google Cloud Source Repositories, GitHub       |
| **Artifact Management**| AWS CodeArtifact                 | Built-in Azure Artifacts              | Google Container Registry, Artifact Registry                     |
| **Third-party Integrations** | Integrations with Jenkins, GitHub Actions, and other CI/CD tools | Extensive integration with GitHub, Docker Hub, Jenkins, Slack | Integrations with GitHub, Bitbucket, and external CI/CD tools    |
| **Ease of Use**        | Easy setup for AWS users; requires some AWS knowledge | User-friendly, especially for those familiar with Azure | Straightforward for GCP users, uses YAML configuration          |
| **Best For**           | Organizations heavily using AWS services | Enterprises using Azure services and Microsoft stack | Organizations using Google Cloud services                        |
| **Compliance & Governance** | Meets various compliance standards (ISO, SOC, HIPAA) | Complies with Microsoft’s compliance offerings (SOC, GDPR, HIPAA) | Complies with Google’s compliance standards (ISO, SOC, GDPR)    |


