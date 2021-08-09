# Trigger AWS Glue Crawler using Lambda
This is the sample Python script using Lambda to start Glue Crawler in AWS. 
## Use Case
Auto trigger crawler run when new data files arriving S3 bucket, so Glue Data Catalog can be most up-to-date.

## Prerequisite
Before creating the Lambda Function using the script, be sure that you have:
- Glue Crawler
- S3 bucket with a folder to put files

## Steps
### Create a IAM service role:
Let’s start with creating a IAM service-linked for Lambda.
- Open the IAM console
- Choose Roles. Then choose Create role.
- Choose a use case: Lambda, Then choose Next: Permissions.
- Search AWSGlueServiceRole policy, check it, and then choose Next: Tags.
- Choose Next: Review. 
- Type in Role name, Then hit Create

### Create a Lambda function
- Open AWS Lambda
- Choose Create function.
- Be sure that Author from scratch is selected, and then configure the following options:
-- For Name, enter a name for your function.
-- For Runtime, choose one of the Python options.
-- For Role, choose Choose an existing role.
-- For Existing role, select the IAM role that we just created.
- Choose Create function.
- Create function with existing IAM role
- In the Function code section, paste code in the Python Script. Be sure to replace REGION and CRAWLER with the name of your AWS Glue Crawler.
- Hit Deploy

### How to add S3 trigger:
- Click the Add Trigger
- Choose S3
- Type in Bucket Name, for example our bucket is: (glue-demo-ascending)
- Select Event type: PUT
- Input Prefix to target the folder: for example we put files in the folder: (input/)
- Click Add

## Demo Video
Coming Soon!
