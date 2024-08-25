# Continuous Integration (CI)

This is a process of triggering auto builds and testing whenever any checkins / merges are happening to the repository, this will ensure that the repos are tested and ensures the errors are detected earlier

## Key things

- **Frequent Integration:** Platform to organize frequent and parallel commits
- **Automated Builds:** Automatically builds the latest code
- **Automated Testing:** Once build is done, automatically testing the changes
- **Immediate Feedback:** Any point of failure, the information is sent to multiple stake holders
- **Deployment Readiness:** Following this, the application is ready for deployment to higher environments most of the time

## **CI Workflow:**

- **Code Commit:** A developer writes code and commits it to a version control system (like Git).
- **Trigger Build:** The commit triggers the CI server to pull the latest code from the repository.
- **Automated Build:** The CI server compiles the code and creates a build.
- **Automated Testing:** The CI server runs automated tests against the build to check for any issues.
- **Feedback:** The CI server provides feedback to the developer, indicating whether the build and tests were successful or if there were any issues.
- **Fixing Issues:** If issues are found, the developer fixes them and recommits the code, repeating the process.

## Popular CI Tools:

- Jenkins
- AWS CodeBuild
- GitHub Actions
- CircleCI
- Travis CI
- Azure Pipelines
- GitLab CI/CD

## Comparision of Popular CI Tools:

| Feature                     | Azure Pipelines               | GitHub Actions                | CircleCI                      | Travis CI                    | GitLab CI/CD                 | Jenkins X                     | AWS CodeBuild                 |
|-----------------------------|-------------------------------|-------------------------------|-------------------------------|------------------------------|------------------------------|-------------------------------|-------------------------------|
| **Supported Platforms**     | Windows, Linux, macOS         | Windows, Linux, macOS         | Linux, macOS                  | Linux, macOS, Windows (via VMs) | Windows, Linux, macOS       | Kubernetes-native             | Linux, Windows                |
| **Parallel Builds**         | Yes                           | Yes                           | Yes                           | Yes                          | Yes                          | Yes                           | Yes                           |
| **Pricing**                 | Free tier available, pay-as-you-go for additional usage | Free tier with limits, Pay-as-you-go for additional usage | Free tier available, pay-as-you-go for additional usage | Free tier with limits, Paid plans available | Free tier with limits, Paid plans available | Open source, Pay-as-you-go for cloud hosting | Pay-as-you-go, billed by the minute |
| **Integrations**            | Azure DevOps, GitHub, Bitbucket | GitHub, Slack, Docker, etc.   | GitHub, Bitbucket, Slack, Docker, etc. | GitHub, Bitbucket, Slack, Docker, etc. | GitLab, Slack, Docker, etc.  | GitHub, Bitbucket, Slack, Docker, etc. | AWS services, GitHub, Bitbucket, etc. |
| **Custom Pipelines**        | YAML-based                    | YAML-based                    | YAML-based                    | YAML or JSON                  | YAML-based                    | YAML-based                     | YAML-based (buildspec.yml)    |
| **Docker Support**          | Native support                | Native support                | Native support                | Native support               | Native support               | Native support                | Native support                |
| **Deployment Options**      | Azure, AWS, GCP, On-premise   | Azure, AWS, GCP, On-premise   | AWS, GCP, On-premise          | AWS, GCP, On-premise         | Azure, AWS, GCP, On-premise  | Azure, AWS, GCP, On-premise   | AWS, On-premise               |
| **Security & Compliance**   | Enterprise-grade security, SOC 2, GDPR | Enterprise-grade security, SOC 2, GDPR | SOC 2, GDPR                   | SOC 2, GDPR                   | SOC 2, GDPR                   | SOC 2, GDPR                   | SOC 2, PCI DSS, HIPAA, GDPR   |
| **Ease of Use**             | Easy to moderate              | Easy                          | Easy                          | Easy                          | Easy                          | Moderate to complex           | Easy                          |
| **Pipeline Visualization**  | Yes, intuitive UI             | Yes, with a UI                | Yes, with a UI                | Yes, with a UI               | Yes, with a UI               | Yes, with a UI                | Yes, with CloudWatch Metrics  |
| **Community & Support**     | Strong community, Microsoft support | Strong community, GitHub support | Strong community, Community and Paid support | Strong community, Community and Paid support | Strong community, GitLab support | Strong community, Community and Paid support | AWS Support, Documentation, and Community |
| **Caching**                 | Built-in                      | Built-in                      | Built-in                      | Built-in                      | Built-in                      | Built-in                      | Built-in                      |
| **Artifact Storage**        | Built-in                      | Built-in                      | Built-in                      | Built-in                      | Built-in                      | Built-in                      | S3, ECR                       |
| **Kubernetes Integration**  | Limited, needs customization  | Limited, needs customization  | Limited, needs customization  | Limited, needs customization | Limited, needs customization | Native support                | Limited, needs customization  |
| **Auto-scaling**            | Yes, based on usage           | Yes, based on usage           | Yes, based on usage           | Yes, based on usage           | Yes, based on usage           | Yes, based on Kubernetes      | Yes, scales automatically     |
| **Configuration as Code**   | Yes, YAML-based               | Yes, YAML-based               | Yes, YAML-based               | Yes, YAML-based               | Yes, YAML-based               | Yes, YAML-based               | Yes, YAML-based               |
| **Hosted Runners**          | Yes, with multiple OS options | Yes, with multiple OS options | Yes, Linux-based              | Yes, with multiple OS options | Yes, with multiple OS options | Yes, Kubernetes-based         | No (runs in managed containers) |
 

_CI is a fundamental practice in modern software development, especially in agile environments, where rapid and reliable delivery of software is crucial._