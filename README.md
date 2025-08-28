# CRUD APP using AWS LAmbda, API Gateway and AWS Dynamo DB 

**AWS Lambda**

1. Go to AWS Lambda Service and click on 
2. Set name as *createBook* and pick runtime as *nodejs 18.x*
3. Copy and paste the code in index.mjs file
5. Hit deploy for every new change


**API gateway**


1. Go to AWS API Gateway Service and click on
2. Click on create *HTTP API*
3. Click on *Add Integration* choose *lambda* and picked the already created function
4. Set a name as *books-api*
5. Hit next and pick *POST* as the verb and modify resource path as *books* to integrate with the function
6. Leave everything else as default and click on create
   -by clicking the API we can see the URL

We can test our API Gateway using Postman or any other preferred tool


**Dynamo DB**


1. Go to AWS Dynano DB and click on create table
2. We can name it as *books* and set partition key as *id*, leave everything else as default
- We can see table data by clicking on explore table items


**Create inline policy to have write permissions on the DB**

1. Go to Lambda function, click on configuration then permissions
2. We must have an existant role with CloudWatch permissions, click on ti to modify it.
3. Clocik on create inline policy
4. Look up for the *dynamodb* service, and add action *putitem*
5. We must specify the region and the corresppondant ARN
6. Generate a name for the policy and then create.


**AWS CloudWatch**

1. GO to AWS Lambda function.
2. Click on monitor, then CloudWatch  logs
3. Inside log groups we will see the app logs
- We can use search log groupto view it as text so it will be easir to search for the errors.


**Create new record using POSTMAN**

1. Go to POSTMAN tool, choose POST verb, paste the URL
2. Go to body/raw/json and paste something like the following:

   {
    "title": "Harry Potter",
    "author": "JK Rowling"
   }
3. Hit send button   
4. If we get the following error, it mease we must add the proper permissions.

-{"message":"User: arn:aws:sts::255587935648:assumed-role/createBook-role-ft5i2b13/createBook is not authorized to perform: dynamodb:PutItem on resource: arn:aws:dynamodb:us-east-1:255587935648:table/books because no identity-based policy allows the dynamodb:PutItem action"}-



**Final steps**

We shall need to delete the folling in order to avoid AWS charges:

- AWS Lambda Function
- AWS API Gateway
- Dynamo DB table created
- Any new role created (just in case)

