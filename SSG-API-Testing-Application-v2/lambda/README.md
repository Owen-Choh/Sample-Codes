# Introduction
This directory is still **WIP**

It will contain POC of obtaining secrets from AWS Secrets Manager.

This POC is meant to showcase how you can put your authentication secrets in AWS Secrets Manager and retrieve them to use when calling our APIs

`lambda_function.py` contains the lambda function POC

- Permissions given to the lambda function:
    - AWSLambdaBasicExecutionRole (AWS managed)
    - KmsDecrypt 
    ```
    {
        "Version": "2012-10-17",
        "Statement": [
            {
                "Sid": "VisualEditor0",
                "Effect": "Allow",
                "Action": "kms:Decrypt",
                "Resource": "*"
            }
        ]
    }
    ```
    - SecretsPolicy  
    ```
    {
        "Version": "2012-10-17",
        "Statement": [
            {
                "Sid": "VisualEditor0",
                "Effect": "Allow",
                "Action": [
                    "secretsmanager:GetSecretValue"
                ],
                "Resource": "*"
            }
        ]
    }
    ```

To import dependencies into AWS Lambda, you can add them via custom layers. The steps to do so are described [here](https://stackoverflow.com/questions/65975883/aws-lambda-python-error-runtime-importmoduleerror)


"errorMessage": "HTTPSConnectionPool(host='uat-api.ssg-wsg.sg', port=443): Max retries exceeded with url: /courses/courseRuns/id/35423?includeExpiredCourses=true (Caused by SSLError(SSLError(524297, '[SSL] PEM lib (_ssl.c:3845)')))",
  "errorType": "SSLError",