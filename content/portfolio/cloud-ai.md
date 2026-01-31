---
title: "Cloud-AI: Serverless ML Pipeline"
date: 2024-11-01
draft: false
tags: ["AWS", "Terraform", "Python", "Serverless", "DynamoDB", "Lambda"]
cover:
  image: ""
  alt: "Cloud AI Pipeline"
showToc: true
---

## Overview

A serverless machine learning inference pipeline built on AWS infrastructure with a Telegram Bot interface for on-demand model predictions.

## Technical Stack

- **Cloud**: AWS Lambda, API Gateway, S3, DynamoDB
- **Infrastructure**: Terraform IaC for reproducible deployments
- **Development**: LocalStack for local testing
- **Runtime**: Dockerized Python for portable ML deployments
- **Interface**: Telegram Bot API for user interaction

## Key Features

- **Serverless Architecture**: Pay-per-use model with AWS Lambda for cost-efficient inference
- **Infrastructure as Code**: Version-controlled, reproducible cloud infrastructure with Terraform
- **State Management**: DynamoDB for lightweight request logging and state management
- **Portable Deployments**: Docker containers for consistent ML model execution
- **User-Friendly Interface**: Telegram bot for easy, on-demand model inference requests

## Architecture

1. User sends request via Telegram Bot
2. API Gateway receives and routes the request
3. Lambda function processes input and runs inference
4. Results stored in DynamoDB and returned to user
5. S3 for model artifacts and data storage

## Links

- [GitHub Repository](https://github.com/Man2Dev/cloud-Ai)
