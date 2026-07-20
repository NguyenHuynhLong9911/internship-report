---
title: "Week 10 Worklog"
date: 2026-07-13
weight: 1
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives

* Deploy the SmartStudy production environment.
* Complete the end-to-end document, AI study, quiz, and result workflows.
* Add monitoring, resolve integration issues, and prepare the final demonstration.

### Tasks Carried Out This Week

| No. | Task | Start Date | Completion Date | Output |
| --- | ---- | ---------- | --------------- | ------ |
| 1 | **Production infrastructure** <br> - Deploy production Cognito, API Gateway, Lambda, S3, SQS, dead-letter queue, and DynamoDB resources with AWS CDK <br> - Keep staging and production resources separated <br> - Validate IAM permissions between services | 13/07/2026 | 14/07/2026 | Production AWS environment |
| 2 | **Frontend delivery and security** <br> - Connect the GitHub `main` branch to AWS Amplify <br> - Deploy the production frontend on the default `amplifyapp.com` domain <br> - Enable AWS WAF protection for Amplify Hosting <br> - Verify Cognito registration and sign-in | 14/07/2026 | 15/07/2026 | Production web application |
| 3 | **Feature integration** <br> - Complete document upload and asynchronous processing <br> - Integrate the study room with the Ollama model running on the self-hosted local AI server <br> - Complete conversation history, quiz generation, answer submission, scoring, and result explanations <br> - Test error handling through the SQS dead-letter queue | 15/07/2026 | 17/07/2026 | End-to-end SmartStudy workflows |
| 4 | **Monitoring and final validation** <br> - Review Lambda and SQS logs and metrics in Amazon CloudWatch <br> - Configure alarms for key Lambda and queue conditions <br> - Fix integration and user-interface issues <br> - Run the final end-to-end test and record the completed project demonstration | 18/07/2026 | 19/07/2026 | Monitored system and final demo video |

### Week 10 Achievements

* Deployed separate staging and production environments in `us-east-1`.
* Automated frontend delivery from GitHub to AWS Amplify and published SmartStudy on the default Amplify domain.
* Completed authentication, document management, AI-assisted study, quiz generation, scoring, and result-review workflows.
* Integrated the Ollama model hosted on a self-hosted local AI server as the project's AI service.
* Added CloudWatch monitoring and completed the final project demonstration on July 19, 2026.

The production environment was kept online through July 30, 2026 for evaluation and demonstration; no cleanup activity was included in this worklog.
