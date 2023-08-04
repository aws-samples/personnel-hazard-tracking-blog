# Industrial Personnel & Hazard Tracking with Amazon Location Services
Link to the AWS Blog: [Industrial Personnel & Hazard Tracking with Amazon Location Service](https://aws.amazon.com/blogs/industries/industrial-personnel-hazard-tracking-with-amazon-location-service/)

## Prerequisites

Before you get started, make sure you have the following prerequisites:
1. An active AWS account
1. Access to the following AWS services: AWS IoT Core, Amazon SQS, AWS Lambda, Amazon Timestream, Amazon Location Services, AWS Amplify, Amazon Cognito, and Amazon API Gateway

## Deployment

1. Go to the GitHub repository here with the needed CloudFormation template and zip files with the Lambda code.  Download the files in the PersonnelTracking folder.
1. Log into your AWS account.
1. Go to the S3 service and create a new S3 bucket, as we will use it to store the required Lambda function code.  If you would like to use an existing S3 bucket, take note of the path to where you want to copy the files.
1. Copy the 4 Lambda code zip files to the S3 bucket.
1. Go to the CloudFormation service and click the button in the top right to Create stack -> With new resources. 
1. Choose Upload a template file and select the file from the repository.
1. Choose Next, and then on the Specify stack details page, provide a stack name.  
1. In the Parameters section, enter the S3 bucket name where the Lambda files reside, e.g. my-tracker-bucket.
1. Choose Next, and continue to choose Next on the subsequent pages until you see the Create Stack option.
1. Check the box to acknowledge that AWS CloudFormation might create IAM resources with custom names.
1. Choose Create Stack to deploy the stack.
1. Monitor the status of the stack. When the status is CREATE_COMPLETE, choose the Resources tab for the CloudFormation stack to confirm that all 39 resources are created.
1. Go to the Outputs tab in the CloudFormation stack, note the "ApiEndpoint" and "CognitoID" values, they will be needed later.
1. Under the Outputs tab in the CloudFormation stack, click on Amplify Console link.
1.	On the AWS Amplify console, under “All apps”, choose the “Device_Map_App” and click on Run build.
1.	Once the app is successfully deployed, click on the link of the main application link
1.	In the main application, enter the API Endpoint and Cognito ID Pool you noted from Step 13, and press submit to Start  Map.  This will load the map.
1.	Optionally, you could also inspect the EventBridge Rules, IoT MQTT Test Client, IoT Events Detector Models from the Outputs tab in the CloudFormation stack.  Links are provided in the CloudFormation outputs and on the web application.

## Clean Up

To terminate all the resources you created throughout this tutorial, select your CloudFormation stack, and click delete. 

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

