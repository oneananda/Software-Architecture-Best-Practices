# Dynamic Feature Branch Deployment

## Overview

This document explains how to configure your development environment to automatically create a live preview site for each feature branch. For instance, if you are working on a ticket with the number `1677` and create a feature branch named `1677`, the goal is to automatically deploy a React-based site accessible via `1677.dev.mysite.com`.

## Prerequisites

- **AWS Account:** Ensure you have permissions for services like Route 53, AWS Amplify (or an alternative CI/CD tool), and other related AWS resources.
- **Domain Setup:** A domain (e.g., `dev.mysite.com`) managed in AWS Route 53 with a wildcard DNS record.
- **CI/CD Pipeline:** A pipeline (e.g., GitHub Actions, AWS CodePipeline, etc.) configured to trigger on branch creation or updates.
- **React Application:** Your project repository is set up with a React-based front end.

