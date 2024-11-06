# Cloud-Based Exponent Calculator

This project implements a serverless **Exponent Calculator** using AWS services. It allows users to calculate the exponentiation of a number using an HTTP API. The calculator is designed with scalability, reliability, and cost-efficiency in mind, making use of AWS Lambda, API Gateway, DynamoDB, and S3.

## Overview

The Cloud-Based Exponent Calculator leverages AWS Lambda to run the calculation logic in response to HTTP requests, API Gateway to expose the calculator as a RESTful API, and DynamoDB for logging the calculations. The web interface (optional) is hosted on Amazon S3, providing a user-friendly front-end to interact with the API.

### Key Features:
- **Serverless**: Fully managed infrastructure with AWS Lambda and API Gateway.
- **Scalable**: Handles large numbers of requests with automatic scaling via Lambda.
- **Persistent Data**: Logs each calculation (input, output, and timestamp) in DynamoDB for future analysis.
- **Web Interface**: Optional simple HTML/JS front-end hosted on S3 for easy interaction with the API.

## Architecture

The application is built with the following AWS components:
- **AWS Lambda**: Used for computing the exponentiation logic.
- **Amazon API Gateway**: Provides a REST API endpoint for the exponentiation request.
- **Amazon DynamoDB**: Stores logs of each calculation, including the base, exponent, and result.
- **Amazon S3**: Hosts the static web page (optional) for users to interact with the API.

### Flow:
1. The user enters the base number and exponent in the front-end web interface.
2. The API Gateway sends the request to AWS Lambda.
3. AWS Lambda performs the exponentiation and logs the result in DynamoDB.
4. The result is returned to the user via the API Gateway.

## Getting Started

### Prerequisites:
Before getting started, you need to have the following:
- An AWS account with permission to use AWS Lambda, API Gateway, DynamoDB, and S3.
- [AWS CLI](https://aws.amazon.com/cli/) installed and configured on your machine.

### Setup:
1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/Cloud-Based-Exponent-Calculator.git
    cd Cloud-Based-Exponent-Calculator
    ```

2. Deploy the serverless stack:
   - Ensure you have the AWS SAM CLI or AWS CloudFormation set up to deploy Lambda functions and API Gateway.
   - Deploy the application using the following command:
     ```bash
     sam deploy --guided
     ```

3. After deployment, you will receive an endpoint URL from API Gateway. Use this URL to make requests to the Exponent Calculator API.

### Example API Request:
To calculate the exponent of 2 to the power of 5, make a `POST` request to the API endpoint with the following JSON payload:

```json
{
  "base": 2,
  "exponent": 5
}

{
  "base": 2,
  "exponent": 5,
  "result": 32,
  "timestamp": "2024-11-06T14:25:00Z"
}


