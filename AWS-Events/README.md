# AWS-Events

- SQS and SNS are important components for scalable, large scale, distributed, cloud-based applications:

![img](./img/1.png)

- SNS is a distributed publish-subscribe service.

- SQS is distributed queuing service.

- Amazon SNS is a fast, flexible, fully managed push notification service that lets you send individual messages or to bulk messages to large numbers of recipients. Amazon SNS makes it simple and cost effective to send push notifications to mobile device users, email recipients or even send messages to other distributed services.
SNS is a distributed publish-subscribe system. Messages are pushed to subscribers as and when they are sent by publishers to SNS.
SNS supports several end points such as email, sms, http end point and SQS. If you want unknown number and type of subscribers to receive messages, you need SNS.With Amazon SNS, you can send push notifications to Apple, Google, Fire OS, and Windows devices , as well as to Android devices in China with Baidu Cloud Push. You can use SNS to send SMS messages to mobile device users in the US or to email recipients worldwide.

- Key Differences
Entity Type
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

## Use Cases

Choose SNS if:

You would like to be able to publish and consume batches of messages.
You would like to allow same message to be processed in multiple ways.
Multiple subscribers are needed.

- SQS is mainly used to decouple applications. SNS distributes several copies of message to several subscribers.
