# Project 3: Serverless Web Application with REST API, DynamoDB, and IAM

## Overview

This repository contains **architecture diagrams** (in multiple formats) for a serverless web application.
The design integrates multiple AWS services to deliver a **secure, scalable, and event-driven application** that supports full CRUD operations with role-based access control.

---

## Architecture Description

The architecture demonstrates how to build a **Serverless REST API** with a web front-end, backed by DynamoDB.
It supports CRUD functionality, secure IAM-based access, and centralized monitoring with CloudWatch.

![AWS Architecture](All%20Formats/AWS%20Arch.png)

### Core AWS Services

1. **Amazon API Gateway**

   * Exposes RESTful endpoints for the backend API.
   * Routes CRUD API requests from end users to AWS Lambda functions.

2. **AWS Lambda**

   * Stateless compute functions implementing business logic.
   * Four key functions handle CRUD operations:

     * **Create Function**
     * **Read Function**
     * **Update Function**
     * **Delete Function**
   * Each function interacts with DynamoDB for persistence.

3. **Amazon DynamoDB**

   * NoSQL database storing application records.
   * Provides highly available, fully managed storage.
   * Integrated with Lambda and logs monitored in CloudWatch.

4. **Amazon S3**

   * Stores and serves front-end static files.
   * Provides origin for the CloudFront distribution.

5. **Amazon CloudFront**

   * Content Delivery Network (CDN) serving the front-end globally.
   * Improves performance, caching, and availability of static assets.

6. **AWS IAM**

   * IAM Users and Roles are managed by the System Admin.
   * IAM Role controls **API Gateway → Lambda → DynamoDB** access.
   * Specific role grants **Read & Edit** permissions on DynamoDB.

7. **Amazon CloudWatch**

   * Collects and aggregates logs from:

     * CloudFront
     * API Gateway
     * Lambda Functions
     * DynamoDB
   * Provides monitoring and observability.

---

## Data Flow

1. **End Users**

   * Access front-end files from **CloudFront** (originating from S3).
   * Send API CRUD requests through **API Gateway**.

2. **API Requests**

   * API Gateway invokes the correct **Lambda function** (Create, Read, Update, Delete).
   * Lambda executes logic and interacts with **DynamoDB** for storage.

3. **System Admin**

   * Manages **IAM Users** and assigns appropriate roles.
   * Roles enforce access control for API and database interactions.

4. **Logs and Monitoring**

   * CloudFront, API Gateway, Lambda, and DynamoDB logs flow into **CloudWatch**.
   * Enables debugging, auditing, and performance monitoring.

---

## Learning Outcomes

* How to design a **serverless full-stack web application** using AWS.
* Implementing CRUD APIs with **API Gateway + Lambda + DynamoDB**.
* Hosting a front-end with **S3 + CloudFront** for global delivery.
* Enforcing **IAM roles** for secure service-to-service communication.
* Monitoring serverless applications using **CloudWatch logs**.

---

## Repository Contents

This repository contains only **architecture diagrams** in multiple formats.
It does not include deployment scripts or source code.

Formats available:

* `AWS Arch.png`
* `AWS Arch.svg`
* `AWS Arch.html`
* `AWS Arch.xml`

All formats represent the same architecture for consistency across visualization tools.
