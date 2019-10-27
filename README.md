# AWS---Create-HA-static-site
A script to create a highly available static site on AWS using cloudfortmation
It deploys a 4 EC2 instances running Apache as an auto scaling group. 
The code for the site itself will be held as a zip file on a S3 bucket. You can modify the paramters file "lb-webserver-params.json" with the S3 bucket name and the IAM role to access it.  

__**Prequisites**__

In order to run this script you'll need to have AWS CLI installed and configured on your machine

**How to run?**

(1) To create network infrastructure run "aws cloudformation create-stack --stack-name project2-infra --template-body file://network.yml --parameters file://network-params.json --region=us-west-2".

(2) To create LB and auto scaling group hosting Apache run "aws cloudformation create-stack --stack-name project2-app --template-body file://lb-webserver.yml --parameters file://network-params.jsonlb-webserver-params.json --region=us-west-2 --capabilities CAPABILITY_IAM".
