# RAG Module

This project deploys an AWS architecture for processing FDA 483 documents and analyzing trends using AWS CDK.

## Prerequisites

- AWS CLI configured with appropriate permissions
- Node.js and npm installed
- Python installed
- AWS CDK installed

## Setup Instructions

1. **Initialize the project:**

    ```bash
    mkdir rag_module
    cd rag_module
    cdk init app --language python
    ```

2. **Install necessary dependencies:**

    ```bash
    pip install aws-cdk.aws-s3 aws-cdk.aws-lambda aws-cdk.aws-sqs aws-cdk.aws-apigateway aws-cdk.aws-ec2 aws-cdk.aws-iam aws-cdk.aws-sagemaker
    ```

3. **Create the stack:**

    Create a file `rag_module_stack.py` with the CDK stack code.

4. **Add Lambda function code:**

    Create a directory `lambda` and add a file `processing.py` with the Lambda function code.

5. **Deploy the stack:**

    ```bash
    cdk deploy
    ```

    This will deploy the stack and output necessary information like S3 bucket name, SQS queue URL, API URL, EC2 instance ID, and SageMaker endpoint name.

## Usage

1. **Upload documents to the S3 bucket:**

    Upload FDA 483 documents to the S3 bucket created by the stack.

2. **Invoke the API:**

    Use the API URL output by the stack to trigger the Lambda function and start processing documents.

## Cleanup

To delete the stack and all resources:

```bash
cdk destroy

## Useful commands

 * `cdk ls`          list all stacks in the app
 * `cdk synth`       emits the synthesized CloudFormation template
 * `cdk deploy`      deploy this stack to your default AWS account/region
 * `cdk diff`        compare deployed stack with current state
 * `cdk docs`        open CDK documentation

Enjoy!
