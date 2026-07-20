---
title: "Week 9 Worklog"
date: 2026-07-06
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives

* Provision the SmartStudy serverless infrastructure with AWS CDK and CloudFormation.
* Deploy and validate the staging environment.
* Integrate authentication, APIs, storage, asynchronous document processing, and the application frontend.

### Tasks Carried Out This Week

| No. | Task | Start Date | Completion Date | Output |
| --- | ---- | ---------- | --------------- | ------ |
| 1 | **Infrastructure as Code and authentication** <br> - Bootstrap AWS CDK in `us-east-1` <br> - Define staging resources and IAM roles <br> - Create an Amazon Cognito User Pool and app client <br> - Add a Pre Sign-up Lambda trigger | 06/07/2026 | 07/07/2026 | Staging foundation and authentication |
| 2 | **Backend and data layer** <br> - Create an API Gateway HTTP API and API Lambda <br> - Create an S3 document bucket <br> - Provision DynamoDB tables for AI jobs, attempts, conversations, conversation messages, document chunks, documents, exams, quizzes, and summaries <br> - Connect API operations to the data layer | 08/07/2026 | 09/07/2026 | Staging API and database resources |
| 3 | **Asynchronous document ingestion** <br> - Create the document-processing SQS queue and dead-letter queue <br> - Implement the Document Ingestion Lambda <br> - Connect S3, SQS, Lambda, and DynamoDB <br> - Validate document metadata and chunk persistence | 10/07/2026 | 11/07/2026 | Document ingestion pipeline |
| 4 | **Staging deployment and integration** <br> - Connect the GitHub repository to AWS Amplify <br> - Deploy the staging branch <br> - Configure frontend environment values for Cognito and API Gateway <br> - Perform initial integration tests with the Ollama endpoint hosted on the local AI server | 11/07/2026 | 12/07/2026 | Deployed staging environment |

### Week 9 Achievements

* Provisioned the staging infrastructure using reusable AWS CDK definitions.
* Integrated Cognito, API Gateway, Lambda, S3, SQS, DynamoDB, and Amplify.
* Completed the asynchronous document-processing workflow with failure handling through a dead-letter queue.
* Deployed the staging frontend from GitHub and prepared the system for production rollout.
