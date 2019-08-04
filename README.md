# Disc Lost and Found
If you are here you are likely interested in how Disc Lost and Found works from a technical perspective. This will give a high level overview of the technologies used and how they all fit together. For the time being, the project is not open source, but I will speak about the inner workings here.

## Technologies Used (not exhaustive)
### Languages
* JavaScript
* HTML
* CSS

### AWS
* API Gateway
* CloudFormation
* CloudFront
* Cognito
* DynamoDB
* IAM
* Lambda
* Route 53
* S3

### Other
* Stripe

## Front End
The front end is built using React. The UI heavily utilizes Material UI to get a consistent and clean look.

### User Requests
The front end sends user requests with AWS-Amplify. These requests hit an API endpoint which will be discussed in further detail in the back end. 

## Back End
The back end is built using the serverless framework and Node.

### User Request Handling
1) User sends a request from the front end
2) Request goes through API Gateway which transforms the request using a customized authorizer
3) API Gateway sends the request to a lambda function
4) Lambda function handles all data processing and sends the result back to API Gateway
5) API Gateway formats the request and sends a response back to the front end
