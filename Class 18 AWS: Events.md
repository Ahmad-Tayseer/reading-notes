# ***Read: Class 18 - AWS: Events***

***

## ***AWS SQS vs SNS***

***

## **What is the difference betweeen SQS and SNS?**

SNS (Simple Notification Service):

    Amazon SNS is a fast, flexible, fully managed push notification service that lets you send individual messages or to bulk messages to large numbers of recipients. Amazon SNS makes it simple and cost effective to send push notifications to mobile device users, email recipients or even send messages to other distributed services.

    SNS is a distributed publish-subscribe system. Messages are pushed to subscribers as and when they are sent by publishers to SNS.

![]()

SQS (Simple Queue Service):

    Amazon SQS is a fully managed message queuing service that enables you to decouple and scale microservices, distributed systems, and serverless applications.

    SQS is distributed queuing system. Messages are not pushed to receivers. Receivers have to poll SQS to receive messages. Messages can be stored in SQS for short duration of time (max 14 days).

![]()

Key Differences:

Entity Type:

    SQS : Queue (similar to JMS, MSMQ).
    SNS : Topic-Subscriber (Pub/Sub system).

Message consumption

    SQS : Pull Mechanism — Consumers poll messages from SQS.
    SNS : Push Mechanism — SNS pushes messages to consumers.

Persistence

    SQS : Messages are persisted for some duration is no consumer available. The retention period value is from 1 minute to 14 days. The default is 4 days.
    SNS : No persistence. Whichever consumer is present at the time of message arrival, get the message and the message is deleted. If no consumers available then the message is lost.

    In SQS the message delivery is guaranteed but in SNS it is not.

Consumer Type

    SQS : All the consumers are supposed to be identical and hence process the messages in exact same way.
    SNS : All the consumers are (supposed to be) processing the messages in different ways.

***

## **What are some use cases for both SNS and SQS?**

Choose SNS if:

- You would like to be able to publish and consume batches of messages.
- You would like to allow same message to be processed in multiple ways.
- Multiple subscribers are needed.

Choose SQS if:

- You need a simple queue with no particular additional requirements.
- Decoupling two applications and allowing parallel a synchronous processing.
- Only one subscriber is needed.

***

[README](README.md)
