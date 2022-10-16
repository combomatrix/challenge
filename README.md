
# Overview Serverless Hardening Lambda

In this tutorial, you'll create a simple serverless web application that enables users to request unicorn rides from the Wild Rydes fleet. The application will present users with an HTML based user interface for indicating the location where they would like to be picked up and will interface on the backend with a RESTful web service to submit the request and dispatch a nearby unicorn. The application will also provide facilities for users to register with the service and log in before requesting rides.
Application Architecture

The application architecture uses AWS Lambda, Amazon API Gateway, Amazon DynamoDB, Amazon Cognito, and AWS Amplify Console. Amplify Console provides continuous deployment and hosting of the static web resources including HTML, CSS, JavaScript, and image files which are loaded in the user's browser. JavaScript executed in the browser sends and receives data from a public backend API built using Lambda and API Gateway. Amazon Cognito provides user management and authentication functions to secure the backend API. Finally, DynamoDB provides a persistence layer where data can be stored by the API's Lambda function.

![Serverless web app](https://d1.awsstatic.com/Test%20Images/Kate%20Test%20Images/Serverless_Web_App_LP_assets-04.094e0479bc43ee7ecbbd1f7cc37ab90b83fe5e73.png)

# Static Web Hosting

AWS Amplify hosts static web resources including HTML, CSS, JavaScript, and image files which are loaded in the user's browser.

# User Management

Amazon Cognito provides user management and authentication functions to secure the backend API.

# Serverless Backend

Amazon DynamoDB provides a persistence layer where data can be stored by the API's Lambda function.

# RESTful API

JavaScript executed in the browser sends and receives data from a public backend API built using Lambda and API Gateway.

## The first task needs 500 as input and the second needs auth key abcd1234sadfsdf and the next task needs the uuid as the response which is obtained from the lambda invocation

This site was built using [GitHub Pages](https://pages.github.com/).

Final hint:

# The root cause is the API authorizer does not have enough permissions to Invoke the Lambda authorizer function

- You need to update the Resource-based policy of the function named "Jamchallenge-auth-lambda-proxy-function-1"

- Open the AWS Console

- Navigate to AWS Lambda service

- Click on the "Functions" on the left hand menu

- Search for the function named "Jamchallenge-auth-lambda-proxy-function-1" and click on it. You will be redirected to the page where you can update the function.

- Click on the "Configuration" tab and click on "Permissions on left hand menu

- Under the "Resource-based policy" you will see permissions currently granted

- Review the policy statement. You will notice the statement only grants the source ARN similar to "arrcaws.execute-apl:$region$aws-account-id:$api-id/"/POST/". The policy statement details will look like below

- Principal: apigateway.amazonaws.com

- Effect: Allow

- Action: lambda:InvokeFunction

- Source ARN: armawsexecute-apl:$region$aws-account-id-Sapl-id/"/POST/

- This ARN represents the POST method. Instead, we need to replace the source ARN with the authorizer ARN similar to "amawsexecute-apt:$region:$aws-account-id:$apl-id/authorizers/Sauthorizer-id You can retrieve the authorizer id from the authorizer configuration in the API Gateway console

- Finally policy statement details should look like below

Principal: apigateway.amazonaws.com

Effect: Allow

Action: lambda:invokeFunction

Source ARN: arcaws.execute-apl:$region:$aws-account-id:$api-id/authorizers/$authorizer-id

Invoke the API and retrieve the response payload. You should receive a response with 200 HTTP status code

![Octocat](https://myoctocat.com/assets/images/base-octocat.svg)
# Octocat

