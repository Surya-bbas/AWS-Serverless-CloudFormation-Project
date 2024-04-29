# AWS-Serverless-RestAPI-Architecture-Project Using CloudFormation
This is a CloudFormation template that sets up the infrastructure for a banking application, allowing users to query banking status via API Gateway Service, which triggers the Lambda function Service to fetch data from an S3 bucket Service and return it as a response.

# Architecture:
![image](https://github.com/Surya-bbas/AWS-Serverless-CloudFormation-Project/assets/99864714/2e05dfc4-1294-4009-bc66-39a6de1d3a4a)

# Resources Used In CloudFormation:

### BankingSystemS3Bucket:
* Creates an S3 bucket named "surya-banking-s3-bucket".

### IAMrole:
* Creates an IAM role named "Allow-S3-Role" with permissions to assume roles for Lambda functions.
* Attaches the managed policy "AmazonS3FullAccess" to grant full access to S3.

### LambdaFunction:
* Creates a Lambda function named "LambdaFunction" with Python 3.12 runtime.
* The function retrieves an object from the S3 bucket and returns its contents.

### bankingRestApi:
* Creates an API Gateway REST API named "Banking System API".

### bankingStatusResource:
* Defines a resource for the API Gateway under the root path.

### getBankingStatusMethod:
* Defines a GET method for the API Gateway resource.
* Integrates with the Lambda function to handle requests.
  
### bankingAPIDeployment:
* Deploys the API Gateway configuration to a stage named "Dev".
  
### lambdaFunctionInvokePermisson:
* Grants permission for API Gateway to invoke the Lambda function.
