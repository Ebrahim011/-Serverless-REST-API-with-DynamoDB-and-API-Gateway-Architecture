# Project 3: Serverless REST API with DynamoDB and API Gateway

## Overview

This repository contains the **architecture diagrams** (in multiple formats) for a serverless REST API project. The diagrams illustrate how different AWS services integrate to deliver a fully managed, scalable, and event-driven application without server management.



---

## Architecture Description

The architecture demonstrates how to build a **Serverless REST API** using AWS services. It is designed to manage simple records (like a to-do list or customer data) and supports full CRUD (Create, Read, Update, Delete) functionality.

![AWS Architecture](All%20Formats/AWS%20Arch.png)

### Core AWS Services

1. **Amazon API Gateway**

   * Exposes RESTful endpoints to clients.
   * Routes incoming HTTP requests to AWS Lambda functions.

2. **AWS Lambda**

   * Stateless compute functions.
   * Each function handles CRUD logic for the API.
   * Connects with DynamoDB for persistent storage.

3. **Amazon DynamoDB**

   * NoSQL database to store application records.
   * Scalable, serverless, and integrates seamlessly with Lambda.

4. **Amazon S3**

   * Hosts the front-end web application.
   * Serves static assets directly to end users.

5. **Amazon CloudFront** *(optional, as shown in the diagram)*

   * Content Delivery Network (CDN) for global distribution of the front-end.
   * Improves performance and availability.

6. **AWS IAM**

   * Provides fine-grained access control between services (API Gateway → Lambda → DynamoDB).
   * Ensures secure API access through roles and permissions.

7. **Amazon CloudWatch**

   * Centralized logging and monitoring.
   * Collects logs from API Gateway, Lambda, and DynamoDB for observability.

---

## Data Flow

1. End user sends a request to the **API Gateway** endpoint.
2. API Gateway forwards the request to the appropriate **Lambda function**.
3. Lambda function processes the logic (CRUD) and interacts with **DynamoDB**.
4. Response is sent back through API Gateway to the client.
5. Logs and metrics are stored in **CloudWatch** for monitoring.
6. Front-end (hosted on **S3/CloudFront**) communicates with the API Gateway.

---

## Learning Outcomes

* Understanding how to design **serverless, event-driven architectures**.
* Using **API Gateway + Lambda** for stateless request handling.
* Leveraging **DynamoDB** as a fully managed NoSQL database.
* Implementing **IAM roles and policies** for secure communication.
* Monitoring with **CloudWatch** for performance and debugging.

---


## Repository Contents

This repository includes only **architecture diagrams** in multiple formats for visualization and sharing purposes.
No source code or deployment scripts are provided.

Formats available:

* `AWS Arch.png`
* `AWS Arch.svg`
* `AWS Arch.html`
* `AWS Arch.xml`

All formats represent the same architecture for easier reference across tools and platforms.
