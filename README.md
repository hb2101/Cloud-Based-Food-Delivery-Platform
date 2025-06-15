"""# AI Photo Search using AWS

This project is a serverless web application that allows users to upload and search photos using natural language queries powered by AI and AWS services. It leverages AWS Lambda, Amazon Lex, Amazon Rekognition, OpenSearch, S3, and API Gateway.

## Features

- Upload images and generate automatic labels using Amazon Rekognition
- Natural language photo search via Amazon Lex and OpenSearch
- Web-based frontend for uploading and searching photos
- Serverless backend with Lambda functions and API Gateway
- IAM roles and permissions configured for secure access

## Architecture

- **Frontend**: Static HTML/CSS/JS using `apigClient.js` to communicate with backend
- **Backend**:
  - `index-photos.py`: Lambda function to process image uploads and label indexing
  - `search-photos.py`: Lambda function to process search queries using OpenSearch
- **AWS Services**:
  - S3 (photo storage)
  - Lambda (serverless compute)
  - API Gateway (REST endpoints)
  - Lex (natural language interface)
  - Rekognition (image analysis)
  - OpenSearch (search indexing)

## Project Structure

AI-Photo-Search-using-AWS-main/
├── Frontend/                # Static website code
├── Lambda_functions/       # Lambda backend code (index/search photos)
├── otherscripts/           # Buildspec files and CloudFormation template
├── photo-album-api-dev-swagger.yaml  # Swagger/OpenAPI definition

## Setup & Deployment

### Prerequisites

- AWS account with IAM roles for Lambda, S3, OpenSearch, Lex
- AWS CLI & SAM/CloudFormation tools

### Steps

1. **Deploy Infrastructure**  
   Use the `photo-search-stack.yaml` CloudFormation script to deploy the stack.

2. **Upload Lambda Functions**  
   Deploy `index-photos.py` and `search-photos.py` using the Lambda console or CI/CD (`backend-buildspec.yml`).

3. **Configure Lex Bot**  
   Create a Lex bot for photo search intent with slot types for labels.

4. **Frontend Deployment**  
   Upload contents of `Frontend/` to an S3 static website bucket.

## Testing

- Upload a photo through the web interface
- Use the search box with queries like:
  - "Show me pictures of beaches"
  - "Find sunset photos"

## Tech Stack

- AWS Lambda
- Amazon Lex
- Amazon Rekognition
- Amazon OpenSearch
- Amazon S3
- API Gateway
- JavaScript (Frontend)
