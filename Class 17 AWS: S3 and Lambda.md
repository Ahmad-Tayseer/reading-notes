# ***Read: Class 16 - AWS: S3 and Lambda***

***

## ***AWS S3***

***

## **What is Amazon S3?**

    Amazon Simple Storage Service (Amazon S3) is an object storage service offering industry-leading scalability, data availability, security, and performance. Customers of all sizes and industries can store and protect any amount of data for virtually any use case, such as data lakes, cloud-native applications, and mobile apps. With cost-effective storage classes and easy-to-use management features, you can optimize costs, organize data, and configure fine-tuned access controls to meet specific business, organizational, and compliance requirements.

![](./Class-16%20images//product-page-diagram_Amazon-S3_HIW.cf4c2bd7aa02f1fe77be8aa120393993e08ac86d.png)

***

## **Use Cases:**

- Build a data lake:

        Run big data analytics, artificial intelligence (AI), machine learning (ML), and high performance computing (HPC) applications to unlock data insights.

- Back up and restore critical data:

        Meet Recovery Time Objectives (RTO), Recovery Point Objectives (RPO), and compliance requirements with S3’s robust replication features.

- Archive data at the lowest cost:

        Move data archives to the Amazon S3 Glacier storage classes to lower costs, eliminate operational complexities, and gain new insights.

- Run cloud-native applications:

        Build fast, powerful mobile and web-based cloud-native apps that scale automatically in a highly available configuration.

## **Some benefits of using Amazon S3:**

- Scale storage resources to meet fluctuating needs with 99.999999999% (11 9s) of data durability.

- Store data across Amazon S3 storage classes to reduce costs without upfront investment or hardware refresh cycles.

- Protect your data with unmatched security, compliance, and audit capabilities.

- Easily manage data at any scale with robust access controls, flexible replication tools, and
organization-wide visibility.

***

## ***AWS Lambda Basics***

***

## **What is AWS Lambda?**

    AWS Lambda is a serverless computing service provided by Amazon Web Services (AWS). The Lambda functions can perform any kind of computing task, from serving web pages and processing streams of data to calling APIs and integrating with other AWS services.

    So, users of AWS Lambda create functions, self-contained applications written in one of the supported languages and runtimes, and upload them to AWS Lambda, which executes those functions in an efficient and flexible manner.

***

## **Some use cases for AWS Lambdas:**

- Individual tasks run for a short time.

- Each task is generally self-contained.

- There is a large difference between the lowest and highest levels in the workload of the application.

***

## **Describe “serverless” to a non-technical friend.**

    The concept of “serverless” computing refers to not needing to maintain your own servers to run these functions. AWS Lambda is a fully managed service that takes care of all the infrastructure for you. And so “serverless” doesn’t mean that there are no servers involved: it just means that the servers, the operating systems, the network layer and the rest of the infrastructure have already been taken care of, so that you can focus on writing application code.

***

## ***CDN***

***

## **What is a CDN?**

    A Content Delivery Network (CDN) is a geographically distributed group of servers that work together to provide fast delivery of Internet content. A CDN allows for the fast transfer of data needed for loading Internet content including HTML pages, javascript files, stylesheets, images, and videos.

![](./Class-16%20images//What-is-Content-Delivery-Network-1024x647.webp)

***

## **How does a CDN work with relation to the website visitor?**

    CDNs work through servers nearest to the website visitor respond to the request. The content delivery network copies the pages of a website to a network of servers that are spread out at geographically different locations, caching the contents of the page. When a user requests a webpage that is part of a content delivery network, the CDN will redirect the request from the originating site’s server to a server in the CDN that is closest to the user and deliver the cached content. CDNs will also communicate with the originating server to deliver any content that has not been previously cached. In turn, the speed is improved by distributing content closer to the website visitors by using a nearby CDN server, causing visitors to experience faster page loading times. In simpler terms, for example, instead of a user in London trying to access a server in LA, which can cause slower Internet speeds, the user would be redirected through a CDN that is geographically closest to them (London, Paris, Stockholm, etc). As of today, the majority of web traffic goes through through CDNs, including traffic from major sites like Facebook, Netflix, and Amazon.

***

## **What are the benefits of employing a CDN?**

    Employing a CDN doesn’t only speed up the delivery of Internet content, it helps protect your website against certain forms of cyber attacks, such as Denial of Service attacks. It protects against these threats because CDNs allow for the handling of more traffic and withstanding hardware failure better than many origin servers. 

***

[README](README.md)
