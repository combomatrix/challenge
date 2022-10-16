
#Overview

In this tutorial, you'll create a simple serverless web application that enables users to request unicorn rides from the Wild Rydes fleet. The application will present users with an HTML based user interface for indicating the location where they would like to be picked up and will interface on the backend with a RESTful web service to submit the request and dispatch a nearby unicorn. The application will also provide facilities for users to register with the service and log in before requesting rides.
Application Architecture

The application architecture uses AWS Lambda, Amazon API Gateway, Amazon DynamoDB, Amazon Cognito, and AWS Amplify Console. Amplify Console provides continuous deployment and hosting of the static web resources including HTML, CSS, JavaScript, and image files which are loaded in the user's browser. JavaScript executed in the browser sends and receives data from a public backend API built using Lambda and API Gateway. Amazon Cognito provides user management and authentication functions to secure the backend API. Finally, DynamoDB provides a persistence layer where data can be stored by the API's Lambda function.

#Static Web Hosting

AWS Amplify hosts static web resources including HTML, CSS, JavaScript, and image files which are loaded in the user's browser.

#User Management

Amazon Cognito provides user management and authentication functions to secure the backend API.

#Serverless Backend

Amazon DynamoDB provides a persistence layer where data can be stored by the API's Lambda function.

#RESTful API

JavaScript executed in the browser sends and receives data from a public backend API built using Lambda and API Gateway.

##The first task needs 500 as input and the second needs auth key abcd1234sadfsdf and the next task needs the uuid as the response which is obtained from the lanbda invocation
