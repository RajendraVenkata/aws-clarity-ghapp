# Clarity App on AWS

Note that this app relies on a private AMI template for statically compiled app deployment.

For a dynamically compiled app that uses public AMIs and open application code, please look instead to https://github.com/vaficionado/aws-demo-app

This demo template will:
- Create a VPC
- Create a subnet
- Create an internet gateway
- Create a security group
- Configure VPC and subnet routing to allow port 80/22 inbound
- Create a Lambda function and SNS subscription/topic for Slack notifications
- Provision a simple Ubuntu EC2 instance with a static Clarity based app which leverages a preexisting keypair, remote-exec provisioners and the awscli to send SNS notifications which are ultimately routed to Slack, including the IP of the instance
- Provision a load balancer in front of the EC2 instance and return the URL
