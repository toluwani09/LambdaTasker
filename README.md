# LambdaTasker

LambdaTasker – A Serverless Task Management API
LambdaTasker is a fully serverless RESTful API for managing tasks, built using AWS Lambda, API Gateway, and DynamoDB.
🔧 AWS Services Used

- Amazon API Gateway – Exposes public endpoints for task operations.
- AWS Lambda – Serverless compute to process business logic.
- Amazon DynamoDB – NoSQL database for storing task data.
- IAM – Manages access permissions securely.
- CloudWatch – Logs all API/Lambda activity for monitoring.

📐 Architecture Diagram

Client → API Gateway → Lambda Functions → DynamoDB
                         ↘ IAM Role ↙

Use Cases

- POST /tasks – Create a new task
- GET /tasks – Retrieve all tasks
- PUT /tasks/{id} – Update a task
- DELETE /tasks/{id} – Delete a task

Functional Requirements

- CRUD operations on task objects.
- Each task has:
  - taskId (UUID)
  - title (String)
  - status (pending/completed)
  - createdAt (timestamp)

 Non-Functional Requirements

- Fully serverless and auto-scalable
- Monitored via CloudWatch
- IAM-secured Lambda access to DynamoDB
- CORS-enabled REST API

 How to Deploy

1. Create a DynamoDB table named 'Tasks' with 'taskId' as the partition key.
2. Deploy Lambda functions for each CRUD operation.
3. Create a REST API using API Gateway and connect it to your Lambda functions.
4. Set IAM roles and permissions for Lambda to access DynamoDB.
5. Test the API with Postman or curl.

