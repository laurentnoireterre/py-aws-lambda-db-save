# Description

Simple python program to save a message triggers by an SNS topic in DynamoDB.

# Packaging

Clone the repository and zip its content
```
cd py-aws-lambda-db-save
zip -r ../py-aws-lambda-db-save.zip .
```

# Installation & Usage 

Connect to AWS console and create a Lambda having this properties:
   - Runtime: `Python 3.6`
   - Trigger: `SNS`
   - Role:
```
Allow: lambda:GetLayerVersion
Allow: lambda:GetLayerVersionPolicy 
Allow: logs:CreateLogGroup
Allow: logs:CreateLogStream
Allow: logs:PutLogEvents
Allow: sns:*

Resource: *
```
   - Environment variables: 
     - Add an environment variable named `dynamodbTableName` and containing the DynamoDB table name where to create the result

Deploy the function code by uploading the zip package.

You can use the `test-sample.json` file to test the function.