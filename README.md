# Serverless engineering Pipeline
This project emulate Noah Gift's lecture on serverless engineering pipeline on AWS (https://www.youtube.com/watch?v=zXxdbtamoa4)

* producer lambda function read data from DynamoDB
* producer lambda function send the data to SQS 
* The consumer lambda function is triggered from every message from SQS
* The consumer lambda function perform NLP analysis using AWS comprehend
* Store the NLP result to S3 bucket.

## Step 1
create bucket, cloud9 instance in the same region

## Step 2
go create an aws lambda function called consumer. It is imperative to create an administrative access for the role. 

## Step 3 
create a table in DynamoDB and create a SQS queue
* DynamoDB: I have created my table named 'fang' with key 'names'
* SQS: I have named my SQS 'producer' 

## Step 4
setup trigger in the lambda function
* the producer lambda function should link to cloudwatch with 1 min rate 
* the consumer lambda function should link to SQS

## Step 5
Now, we will deploy the Lambda Functions. Before we do that, we'll have to install all the necessary packages(python-json-logger, boto3, wikipedia and pandas at the folder for the consumer function). The command is as (pip3 install python-json-logger --target ../) Then we'll deploy the functions by right clicking on the lambda function upload icons on the right. The process is the same for the consumer function. 

## Step 6 
disable the trigger when you are finished with your project and stop all instance to avoid additional cost.
