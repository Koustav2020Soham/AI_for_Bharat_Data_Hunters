Architecture Pattern: Document a Serverless Event-Driven Architecture. Explain the flow from Amazon API Gateway to AWS Lambda (Microservices) and AWS Step Functions for complex grievance orchestration.

AI & Vision Integration: Detail the implementation of Amazon Rekognition for biometric face matching and Amazon Bedrock (Claude 3) for two distinct use cases:

RAG-based AI Scheme Navigator (Retrieval-Augmented Generation).

NLP Domain Classification for grievance routing.

API Specification: Include a full REST API table with methods, endpoints, and backend mappings for:

/auth/verify (Biometric login)

/vote/submit (Secure ballot + GPS logging)

/analytics/turnout (Real-time heatmap data)

/grievance/report (AI-driven routing)

/schemes/chat (Conversational assistant)

Data Modeling: Define DynamoDB schemas including Partition/Sort keys for the WorkerRegistry (WardID/Domain) and VoterMetrics (BoothID/Timestamp).

Security & Operations: Outline AWS Cognito JWT-based authentication, AWS KMS encryption at rest, and Amazon CloudWatch for real-time monitoring of voter turnout spikes.

Visuals: Generate a Mermaid.js sequence diagram showing the end-to-end flow from citizen grievance submission to municipal worker notification.
