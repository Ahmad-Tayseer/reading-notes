# ***Read: Class 16 - AWS: Cloud Servers***

***

## ***AWS EC2***

***

## **What is an EC2 Instance?**

    Amazon Elastic Compute Cloud (Amazon EC2) offers the broadest and deepest compute platform, with over 500 instances and choice of the latest processor, storage, networking, operating system, and purchase model to help you best match the needs of your workload. It is the first major cloud provider that supports Intel, AMD, and Arm processors, the only cloud with on-demand EC2 Mac instances, and the only cloud with 400 Gbps Ethernet networking.

***

## **Use Cases:**

- Run cloud-native and enterprise applications:

        Amazon EC2 delivers secure, reliable, high-performance, and cost-effective compute infrastructure to meet demanding business needs.

- Scale for HPC applications:

        Access the on-demand infrastructure and capacity you need to run HPC applications faster and cost-effectively.

- Develop for Apple platforms:

        Build, test, and sign on-demand macOS workloads. Access environments in minutes, dynamically scale capacity as needed, and benefit from AWS’s pay-as-you-go pricing.

- Train and deploy ML applications:

        Amazon EC2 delivers the broadest choice of compute, networking (up to 400 Gbps), and storage services purpose-built to optimize price performance for ML projects.

## **Provide 1 reason to use ECS instead of Heroku:**

    ECS offers the best price performance for machine learning training, as well as the lowest cost per inference instances in the cloud. More SAP, high performance computing (HPC), ML, and Windows workloads run on AWS than any other cloud.

***

## ***EC2 For Humans***

***

## **Where can we find EC2 on the AWS Console?**

To connect to your instance using the browser-based client from the Amazon EC2 console:

- Open the Amazon EC2 console at https://console.aws.amazon.com/ec2/ (Links to an external site.).
- In the navigation pane, choose Instances.
- Select the instance and choose Connect.
- Choose EC2 Instance Connect.
- Verify the user name and choose Connect to open a terminal window.

***

## **The general difference between T2 Micro and XL:**

- T2 instances are a low-cost, general purpose instance type that provides a baseline level of CPU performance with the ability to burst above the baseline when needed.

- X1 Instances are a part of the Amazon EC2 memory-optimized instance family and are designed for running large-scale and in-memory applications in the AWS Cloud.

- Compared to other EC2 instances, X1 instances have one of the lowest price per GiB of RAM, and are ideal for running in-memory databases like SAP HANA, big data processing engines like Apache Spark or Presto, and high-performance computing (HPC) applications.

***

## ***Elastic Beanstalk***

***

    It is an easy-to-use service that deploys managesand scales web apps and sevices for you.

## **Relationship Between EC2 and Elastic Beanstalk:**

    Elastic Beanstalk is one layer of abstraction away from the EC2 layer. Elastic Beanstalk will setup an "environment" for you that can contain a number of EC2 instances, an optional database, as well as a few other AWS components such as a Elastic Load Balancer, Auto-Scaling Group, Security Group.

## **Benefits of Using Elastic Beanstalk:**

- Timesaving server configuration.
- Powerful customization.
- Cost-effective price point.

***

[README](README.md)
