# AWS

## What is an EC2 Instance?

Amazon Elastic Compute Cloud (Amazon EC2) provides scalable computing capacity in the Amazon Web Services (AWS) Cloud. Using Amazon EC2 eliminates your need to invest in hardware up front, so you can develop and deploy applications faster. You can use Amazon EC2 to launch as many or as few virtual servers as you need, configure security and networking, and manage storage. Amazon EC2 enables you to scale up or down to handle changes in requirements or spikes in popularity, reducing your need to forecast traffic.

## Name 2 use cases for EC2

1. Virtual computing environments, known as instances

2. Preconfigured templates for your instances, known as Amazon Machine Images (AMIs), that package the bits you need for your server (including the operating system and additional software)

## What is Elastic Beanstalk?

AWS Elastic Beanstalk is an easy-to-use service for deploying and scaling web applications and services developed with Java, .NET, PHP, Node.js, Python, Ruby, Go, and Docker on familiar servers such as Apache, Nginx, Passenger, and IIS.

## Elastic Beanstalk

- EC2 is Amazon's service that allows you to create a server (AWS calls these instances) in the AWS cloud. You pay by the hour and only what you use. You can do whatever you want with this instance as well as launch n number of instances.

- Elastic Beanstalk is one layer of abstraction away from the EC2 layer. Elastic Beanstalk will setup an "environment" for you that can contain a number of EC2 instances, an optional database, as well as a few other AWS components such as a Elastic Load Balancer, Auto-Scaling Group, Security Group. Then Elastic Beanstalk will manage these items for you whenever you want to update your software running in AWS. Elastic Beanstalk doesn't add any cost on top of these resources that it creates for you. If you have 10 hours of EC2 usage, then all you pay is 10 compute hours.

## Some benefits of using Elastic Beanstalk

- Get the ability to deploy a variety of applications on AWS, coded in a variety of programming languages like PHP, Java, Python, Ruby, Node.js, and Go
- Support for web and application containers, including Docker.
- Selection of the most appropriate EC2 instance types that match the processing and memory requirements of your application.
- Support for both Linux and Windows Server based environments.
- Full control over the AWS resources that power your app, along with the complete ability to adjust the various configurations and settings right from the Elastic Beanstalk management console.
