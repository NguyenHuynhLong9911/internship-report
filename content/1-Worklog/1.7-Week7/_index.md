---
title: "Week 7 Worklog"
date: 2026-05-25
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives

* Agree on the official idea for the group project.
* Identify the problem, target users, and core project features.
* Explore AWS services that could support each system component.
* Perform an initial assessment of service availability, account permissions, and cost.

### Agreed Project Idea

The group agreed to develop **SmartStudy AI**, a platform that supports learning from documents. The proposed system would allow users to upload learning materials, interact with an AI assistant, generate quizzes, and review learning results. This was the initial direction, and the architecture still required validation before implementation.

### Tasks completed this week

| No. | Task | Start Date | Completion Date | Result |
| --- | ---- | ---------- | --------------- | ------ |
| 1 | **Agree on the SmartStudy AI idea** <br> - Consolidate the proposed ideas <br> - Identify the learning problem to address <br> - Agree on the target users and core features <br> - Outline the initial user flow | 25/05/2026 | 27/05/2026 | The group agreed on the initial direction and scope |
| 2 | **Explore available AWS services** <br> - Research services for the frontend, authentication, API, and backend <br> - Explore options for storage, asynchronous processing, data, and monitoring <br> - Review AI services that could support RAG and quiz generation <br> - Check initial account, permission, and cost constraints | 28/05/2026 | 30/05/2026 | Produced a list of candidate services for further evaluation |
| 3 | **Outline the initial solution** <br> - Map candidate services to system components <br> - Discuss document upload and AI processing flows <br> - Record technical risks and assumptions requiring validation | 30/05/2026 | 31/05/2026 | Completed a preliminary architecture that was not yet considered final |

### Week 7 Achievements

* Agreed on the **SmartStudy AI** idea and its main product capabilities.
* Identified the frontend, authentication, backend, storage, data, queue, monitoring, and AI components requiring research.
* Created a candidate list including Amplify, Cognito, API Gateway, Lambda, S3, SQS, DynamoDB, and CloudWatch.
* Explored Amazon Bedrock as an initial AI option without yet confirming its availability.
* Completed a preliminary architecture for validation and revision in later weeks.
