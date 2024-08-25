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

_CI is a fundamental practice in modern software development, especially in agile environments, where rapid and reliable delivery of software is crucial._