# Dynamic Feature Branch Deployment

## Overview

This document explains how to configure your development environment to automatically create a live preview site for each feature branch. For instance, if you are working on a ticket with the number `1677` and create a feature branch named `1677`, the goal is to automatically deploy a React-based site accessible via `1677.dev.mysite.com`.

## Prerequisites

- **AWS Account:** Ensure you have permissions for services like Route 53, AWS Amplify (or an alternative CI/CD tool), and other related AWS resources.
- **Domain Setup:** A domain (e.g., `dev.mysite.com`) managed in AWS Route 53 with a wildcard DNS record.
- **CI/CD Pipeline:** A pipeline (e.g., GitHub Actions, AWS CodePipeline, etc.) configured to trigger on branch creation or updates.
- **React Application:** Your project repository is set up with a React-based front end.

## Architecture Overview

- **Wildcard DNS Record:** A record (e.g., `*.dev.mysite.com`) in Route 53 that routes any subdomain to your deployment endpoint.
- **CI/CD Integration:** Automation to detect new feature branches and deploy them dynamically.
- **Custom Subdomain Mapping:** Map each branch (e.g., `1677`) to a corresponding subdomain (`1677.dev.mysite.com`).

## Implementation Steps

### 1. Configure Wildcard DNS in Route 53

Create a wildcard record so that any subdomain under `dev.mysite.com` is routed appropriately.

Example using AWS CLI:

```
aws route53 change-resource-record-sets --hosted-zone-id YOUR_HOSTED_ZONE_ID --change-batch '{
  "Changes": [
    {
      "Action": "UPSERT",
      "ResourceRecordSet": {
        "Name": "*.dev.mysite.com",
        "Type": "A",
        "AliasTarget": {
          "HostedZoneId": "ALIAS_HOSTED_ZONE_ID",
          "DNSName": "your-load-balancer-or-cloudfront-domain",
          "EvaluateTargetHealth": false
        }
      }
    }
  ]
}'
```

### 2. Set Up Your CI/CD Pipeline

Configure your CI/CD pipeline to trigger builds and deployments based on branch changes. Ensure your branch naming follows a consistent pattern (e.g., using the ticket number).

#### Example: GitHub Actions Workflow

```
name: Deploy Feature Branch

on:
  push:
    # Adjust the branch pattern as needed
    branches:
      - 'feature/*'
      - '[0-9]+'

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Code
        uses: actions/checkout@v2

      - name: Install Dependencies
        run: npm install

      - name: Build Application
        run: npm run build

      - name: Configure AWS Credentials
        uses: aws-actions/configure-aws-credentials@v1
        with:
          aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
          aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          aws-region: us-east-1

      - name: Deploy to AWS Amplify
        run: |
          # Example: Publish the build using Amplify CLI
          amplify publish --yes
```

### 3. Map the Custom Subdomain

#### Option A: Using AWS Amplify Console

- **Connect your Repository:** Link your repository to AWS Amplify.
- **Automatic Branch Deployments:** Amplify will detect new branches (e.g., `1677`) and automatically deploy them.
- **Custom Domain Mapping:**  
  In the Amplify Console, add your custom domain (e.g., `dev.mysite.com`) and map the branch `1677` to `1677.dev.mysite.com`.

#### Option B: Manual DNS Updates with Automation

- Use a Lambda function or a CI/CD script to update Route 53 records when a new branch is deployed.
- Programmatically create an A/alias record for the subdomain (e.g., `1677.dev.mysite.com`) pointing to the new deployment endpoint.

### 4. Cleanup and Environment Management

- **Auto-teardown:** Once a feature branch is merged or closed, trigger a cleanup process to tear down the preview environment and remove the DNS record.
- **Cost Control:** Ensure temporary environments are automatically removed to control AWS costs.

## Final Notes

Implementing dynamic feature branch deployments allows for:
- **Rapid Review Cycles:** Each feature branch gets its own environment for QA and stakeholder demos.
- **Isolation:** Testing features in isolation before merging them into the main branch.
- **Automation:** Reducing manual overhead in deployment and DNS management.

---
