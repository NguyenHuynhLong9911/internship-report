---
title: "Building an AI Gateway to Amazon Bedrock with Amazon API Gateway"
date: 2026-07-21
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# Building an AI Gateway to Amazon Bedrock with Amazon API Gateway

When multiple applications use foundation models, direct calls to Amazon Bedrock can make access control, quotas, costs, and API lifecycle management more difficult. The AWS article introduces an **AI gateway** that places Amazon API Gateway in front of Amazon Bedrock to provide a centralized and governed access layer.

![AI gateway architecture for Amazon Bedrock](/internship-report/images/3-BlogsTranslated/3.3-Blog3/ai-gateway.png)

*Figure 1: Reference architecture using API Gateway and Lambda to govern access to Amazon Bedrock.*

## The problem addressed

In an enterprise environment, an AI gateway needs to do more than forward requests:

- Authenticate and authorize users or applications.
- Apply rate limits and quotas by tenant or API key.
- Support usage and cost controls.
- Manage API versions and canary releases.
- Stream model responses in real time.
- Add protection and content controls through services such as AWS WAF.

The pattern allows clients to retain an interface similar to the Bedrock API while governance policies are enforced at the gateway.

## Architecture components

### Amazon Route 53

Route 53 is optional and maps a custom domain to the API Gateway endpoint. Clients can use the default API Gateway endpoint when a dedicated domain is unnecessary.

### Amazon API Gateway

API Gateway is the main entry point. It receives requests and applies authorization, throttling, usage plans, and stage management. Response streaming allows generated output to reach clients incrementally instead of waiting for the entire model response.

### Lambda authorizer

The Lambda authorizer validates a request before access is granted. The reference implementation validates JWTs from an existing identity system, but Amazon Cognito or other API Gateway authorization mechanisms can also be used.

### Lambda integration

The integration Lambda acts as a dynamic request forwarder. It captures the headers, body, and parameters, signs the request with AWS Signature Version 4, and forwards it to the appropriate Bedrock endpoint. This design can support additional Bedrock APIs without defining a dedicated gateway route for every operation.

### Amazon Bedrock

Bedrock provides foundation models and AI capabilities. Clients do not need to manage AWS credentials for direct Bedrock access because request signing occurs in the integration layer.

## Request flow

1. The client calls the custom domain or API Gateway endpoint.
2. API Gateway applies traffic controls and passes identity information to the Lambda authorizer.
3. After authorization, the request reaches the integration Lambda.
4. Lambda preserves the request details, signs the request with SigV4, and calls the corresponding Amazon Bedrock API.
5. The response returns to the client; response streaming can expose output while the model is still generating it.

## Deployment and enhancements

The reference solution can be deployed with AWS CloudFormation. The walkthrough initially uses a private API Gateway with authorization disabled for infrastructure testing, after which appropriate security controls should be enabled.

Important enhancement options include:

- Rate limiting and throttling to prevent a tenant from consuming excessive capacity.
- Private, Regional, or edge-optimized endpoints based on the access pattern.
- Stages and canary deployments for safer releases.
- AWS WAF integration to help protect the endpoint.
- Prompt or response caching to reduce latency and repeated model costs.
- Sensitive-content filtering in the integration layer alongside Amazon Bedrock Guardrails.

## Operational considerations

An AI gateway introduces another operational layer, so latency, Lambda errors, API Gateway quotas, and cost should be monitored. Authorization should not remain disabled in production. The integration Lambda's IAM permissions should follow least privilege and allow only the required Bedrock operations.

## Conclusion

The AI gateway pattern provides a unified entry point for Amazon Bedrock and separates governance policies from client applications. API Gateway controls access and traffic, Lambda handles authorization and signed request forwarding, and Bedrock supplies model capabilities. The pattern is useful when an organization needs to govern AI usage across multiple applications or tenants at scale.

### Reference

[Building an AI gateway to Amazon Bedrock with Amazon API Gateway](https://aws.amazon.com/blogs/architecture/building-an-ai-gateway-to-amazon-bedrock-with-amazon-api-gateway/) — AWS Architecture Blog, November 19, 2025.
