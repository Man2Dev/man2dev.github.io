---
title: "Cloud-AI: Serverlose ML-Pipeline"
date: 2024-11-01
draft: false
tags: ["AWS", "Terraform", "Python", "Serverless", "DynamoDB", "Lambda"]
cover:
  image: ""
  alt: "Cloud AI Pipeline"
showToc: true
---

## Überblick

Eine serverlose Machine-Learning-Inferenz-Pipeline auf AWS-Infrastruktur mit Telegram-Bot-Schnittstelle für On-Demand-Modellvorhersagen.

## Technologie-Stack

- **Cloud**: AWS Lambda, API Gateway, S3, DynamoDB
- **Infrastruktur**: Terraform IaC für reproduzierbare Deployments
- **Entwicklung**: LocalStack für lokale Tests
- **Runtime**: Docker-Container für portable ML-Deployments
- **Schnittstelle**: Telegram Bot API für Benutzerinteraktion

## Hauptfunktionen

- **Serverlose Architektur**: Pay-per-Use-Modell mit AWS Lambda für kosteneffiziente Inferenz
- **Infrastructure as Code**: Versionskontrollierte, reproduzierbare Cloud-Infrastruktur mit Terraform
- **Zustandsverwaltung**: DynamoDB für leichtgewichtige Request-Protokollierung
- **Portable Deployments**: Docker-Container für konsistente ML-Modellausführung
- **Benutzerfreundliche Schnittstelle**: Telegram-Bot für einfache On-Demand-Inferenzanfragen

## Links

- [GitHub Repository](https://github.com/Man2Dev/cloud-Ai)
