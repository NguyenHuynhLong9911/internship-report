---
title: "Week 8 Worklog"
date: 2026-06-29
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives

* Revise the initial architecture based on technical availability, cost, and project constraints.
* Establish the main frontend, backend, authentication, storage, asynchronous processing, and AI workflows.
* Begin implementing the SmartStudy user interface and backend APIs.

### Architecture Decisions

The team could not purchase a custom domain through Amazon Route 53 and could not use Amazon Bedrock. Therefore, SmartStudy would use the default AWS Amplify domain and a model hosted with Ollama on a self-hosted local AI server. AWS Secrets Manager and AWS CloudTrail were also removed from the implementation scope. The revised serverless design centered on AWS Amplify, AWS WAF, Amazon Cognito, Amazon API Gateway, AWS Lambda, Amazon S3, Amazon SQS, Amazon DynamoDB, and Amazon CloudWatch.

### Tasks Carried Out This Week

| No. | Task | Start Date | Completion Date | Output |
| --- | ---- | ---------- | --------------- | ------ |
| 1 | **Architecture revision** <br> - Review the original diagram and project constraints <br> - Remove Route 53, Bedrock, Secrets Manager, and CloudTrail from the target architecture <br> - Add SQS, a dead-letter queue, WAF, GitHub deployment, and the external Ollama server <br> - Define separate staging and production environments | 29/06/2026 | 01/07/2026 | Revised architecture design |
| 2 | **Backend and data design** <br> - Define HTTP APIs for authentication, document management, conversations, quizzes, exams, and attempts <br> - Design S3 document storage and asynchronous ingestion through SQS <br> - Design DynamoDB entities and access patterns <br> - Define the integration contract with the Ollama API | 02/07/2026 | 03/07/2026 | API and data model |
| 3 | **Frontend implementation** <br> - Build the landing page, authentication flow, dashboard, document library, study room, practice, and result pages <br> - Connect the frontend structure to the planned backend APIs <br> - Prepare the GitHub repository and branch workflow for Amplify deployment | 04/07/2026 | 05/07/2026 | Initial SmartStudy web application |

### Week 8 Achievements

* Established an implementable architecture that matched the available AWS services and project budget.
* Defined the document upload, asynchronous ingestion, AI question-answering, and quiz workflows.
* Selected Ollama on a self-hosted local AI server as the AI model host instead of Amazon Bedrock.
* Completed the initial frontend screens and backend contracts required for infrastructure integration in Week 9.
