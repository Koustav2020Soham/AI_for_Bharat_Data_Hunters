# Technical Design:

## 1. System Architecture
Our project follows a serverless, event-driven architecture to ensure high availability and cost-efficiency.

### Core Components
* **Compute:** AWS Lambda for backend logic and AWS Step Functions for grievance routing orchestration.
* **Intelligence:** Amazon Bedrock (Claude 3) for the recommendation engine and Amazon Rekognition for image-based grievance verification.
* **Storage:** Amazon DynamoDB for NoSQL storage of voter records and worker registries; Amazon S3 for storing uploaded evidence images.
* **Geo-Services:** Amazon Location Service for geofencing and mapping citizen location to municipal wards.

## 2. Data Models
### Worker Registry (DynamoDB)
* **Partition Key:** `WardID` (String)
* **Sort Key:** `Domain` (e.g., Road, Water, Waste)
* **Attributes:** `WorkerName`, `WorkerID`, `PhoneNumber`, `Email`

## 3. System Flow
1. **Auth:** User authenticates via **AWS Cognito** using biometric Face Recognition.
2. **Process:** Grievance data is passed to **Amazon Bedrock**, which classifies the domain.
3. **Route:** **AWS Lambda** queries the Worker Registry and triggers an **Amazon SNS** alert to the identified worker.
