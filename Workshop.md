# Workshop

---
## 1.0 Apache Kafka Introduction

### 1.1 What is Apache Kafka?

Apache Kafka is an event streaming platform, which combines three key capabilities for event streaming:

* Publish and subscribe to streams of events, including continuous importation and exportation of the data from other systems.
* Store streams of events durably and reliably for as long as you want.
* Process streams of events as they occur.

[Learn More](URL "https://kafka.apache.org/documentation/")

### 1.2 Apache Kafka Architecture

![ArchitectureIntro](https://snipboard.io/DISyBw.jpg)

Perhaps one of the reasons for the success of Kafka is that its architecture is actually relatively simple, while still being highly scalable and fault tolerant.

### 1.3 Apache Kafka Components

Below is the list of components available in the Kafka architecture.

![ArchitectureComponents](https://snipboard.io/CTd9yk.jpg)

1.	**Kafka Producer**: The producer acts as a sender. It is responsible for sending a message or data. It does not send messages directly to consumers. It pushes messages to Kafka Server or Broker. The messages or data are stored in the Kafka Server or Broker. Multiple producers can send a message to the same Kafka topic or different Kafka topics.
2.	**Kafka Consumer**: The consumer acts as the Receiver. It is responsible for receiving or consuming a message. But It does not consume or receive a message directly from Kafka Producer. The consumer can request a message from the Kafka broker. If the Kafka Consumer will have enough permissions, then it gets a message from the Kafka Broker.
3.	**Kafka Broker**:  The Kafka Broker is nothing but just a server. In simple word, A broker is just an intermediate entity that exchange message between a producer and a consumer. For Kafka Producer, it acts as a receiver, and for Kafka Consumer, it acts as a sender. In the Kafka cluster, there can be one or more Kafka brokers.
4.	**Kafka Cluster**: Now first understand, what is a cluster? A cluster is a common terminology in the distributed computing system. It is nothing but just a group of computers that are working for a common purpose. Kafka is also a distributed system, so it also has a cluster having a group of servers called brokers.
5.	**Kafka topic**: It is one of the most important components of Kafka. Kafka Topic is a unique name given to a data stream or message stream. there can be multiple topics in a cluster. Multiple producers can also send to the same topic. If any consumer wants to consume the message, then it subscribes to the topic present in Kafka Broker. Now all the messages coming to that topic will be delivered to the consumer. Each topic specifies different types of messages.
6.	**Kafka Partitions**: Kafka is a distributed system. In such a scenario, the data or message is divided into small subparts, known as partitions and distribute on different machine to store. Each partition carries data within it having an offset value. The data is always written in a sequential manner. We can have an infinite number of partitions with infinite offset values.
7.	**Kafka Offsets**: In Kafka, a sequence number is assigned to each message in each partition of a Kafka topic. This sequence number is called Offset. As soon as any message arrives in a partition, a number is assigned to that message. For a given topic, different partitions have different offsets. The offset number is always local to the topic partition. There is not any offset that is global to the topic or each partition of the topic.
8.	**Kafka Consumer Group**: Multiple consumers combined to share the workload. It is just like dividing a piece of large task among multiple individuals. There can be multiple consumer groups subscribing to the same or different topics. Two or more consumers belonging to the same consumer group do not receive the common message. They always receive a different message because the offset pointer moves to the next number once the message is consumed by any of the consumers in that consumer group.
9.	**Zookeeper**: Kafka uses Zookeeper for coordination and to track the status of Kafka cluster nodes. It also keeps track of Kafka topics, partitions, offsets, etc. No Kafka server can run without a zookeeper server. It is mandatory to run the zookeeper server.


### 1.4 Apache Kafka Cluster Architecture

![ArchitectureCluster](https://snipboard.io/wNZjpX.jpg)


### 1.5 Apache Kafka Topics and Partitions

![ArchitectureCluster](https://snipboard.io/o98xAd.jpg)


[Learn More](URL "https://dzone.com/articles/kafka-consumer-architecture-consumer-groups-and-su")


### 1.6 Why Is Apache Kafka so Popular?

* **Scalability**: The scalability of a system is determined by how well it can maintain its performance when exposed to changes in application and processing demands. Apache Kafka has a distributed architecture capable of handling incoming messages with higher volume and velocity. As a result, Kafka is highly scalable without any downtime impact.
* **High Throughput**: Apache Kafka is able to handle thousands of messages per second. Messages coming in at a high volume or a high velocity or both will not affect the performance of Kafka.
* **Low Latency**: Latency refers to the amount of time taken for a system to process a single event. Kafka offers a very low latency, which is as low as ten milliseconds.
* **Fault Tolerance**: By using replication, Kafka can handle failures at nodes in a cluster without any data loss. Running processes, too, can remain undisturbed. The replication factor determines the number of replicas for a partition. For a replication factor of ‘n,’ Kafka guarantees a fault tolerance for up to n-1 servers in the Kafka cluster.
* **Reliability**: Apache Kafka is a distributed platform with very high fault tolerance, making it a very reliable system to use.
* **Durability**: Data present on the Kafka cluster is allowed to remain persistent more on the cluster than on the disk. This ensures that Kafka’s data remains durable.


### 1.7 Apache Kafka APIS

* **Producer API**: An application can publish a stream of records to a Kafka topic using the Producer API.
* **Consumer API**: An application can subscribe to one or more topics and also process the stream of records generated to them using this API.
* **Streams API**: The streams API enables applications to convert input streams to output streams, which is accomplished by consuming an input stream from one or more topics and producing an output stream from one or more output topics. Furthermore, to act as a stream processor, consuming an input stream from one or more topics and producing an output stream to one or more output topics, effectively transforming the input streams into output streams, the streams API permits an application.
* **Connector API**: The Connector API is used to connect Kafka topics to existing applications or data systems. For example, a connector to a relational database might capture every change to a table.

[Learn More](URL "https://www.upgrad.com/blog/apache-kafka-architecture/")


### 1.8 Kafka Limitations

While Kafka is both a powerful and flexible stream processing platform, it is not designed for every use case and does have some drawbacks.

* An exception to the rule is that Apache Kafka does not come with a complete set of monitoring and management tools. Because of this, new ventures or enterprises avoid using Kafka.
* A message being tweaked by the Kafka broker requires system calls. In case the message needs some work, its performance of Kafka is reduced. So, it is advisable to keep the message the same.
* When there are more than one Kafka Queue in the Kafka Cluster, Apache Kafka can be a bit clumsy.

[Learn More](URL "https://www.interviewbit.com/blog/kafka-architecture/")


### 1.9 How it works?

Apache Kafka is a distributed system consisting of producers, servers, and clients. Kafka is run as a cluster of one or more servers, also called ‘brokers’, which receives the messages that the producer sends and the consumer, who is subscribed to one or more producers receives the message. It is important to mention that into the brokers or servers, the messages that are sent by the producers are stored in a queue data structure, that receives and delivers the message in a first-in, first-out way. Normally when a message is delivered, it is removed from the queue and there is no chance to get the message back. However, Apache Kafka count with some strategies that will help us to keep the messages during more time if we want to keep the message in the broker.

![ArchitectureProCon](https://snipboard.io/FE0q1G.jpg)


Now, we are going to explain in a deeper way the functioning of Apache Kafka. In Kafka, we could assign a Topic which refers to the cluster of servers that we are going to use to store the messages that are sent by the producers. In addition, each message that is stored in the queue data structure is named as a ‘Record’.  For example, a topic could be like a folder in a filesystem and the records are files.  It is important to mention that a topic could be divided into partitions, each topic can have one or more partitions and we need to specify the number of partitions that we want to have in the topic. 
It is important to mention that to have an order each message should have a partition key, which will assign the message to a specific partition. If we did not assign a partition key, the message is going to be stored in all the partitions, even if the message is sent by the same producer.

![TopicLay](https://snipboard.io/UCtfPm.jpg)

Each message will be stored in the broker and will receive a unique identifier, also called ‘offset’. Something interesting about Kafka is that it stores the messages in the broker, like a database, to be able to recover the messages later if it is necessary. The producers use the identifiers to read the messages, they read from the oldest to the newest messages.
As we mentioned before Kafka works in a distributed way, and each cluster may contain many brokers as needed. It is very important that the number of the partitions match the number of the brokers, and in this way each broker will be in charge of a single partition of the topic.
Each broker in a cluster has an ID that uniquely identifies it and holds at least one topic partition. When constructing a topic, we must configure something called Replication Factor in order to set the number of divisions in each broker. The replication factor allows us to store a backup of a certain partition in other brokers to avoid the loss of information.  In addition, it is important to understand the concept Partition Leader. The leader of each partition in a broker that contains a topic is the only leader that can be present in that partition. Only the leader receives the messages; the backups simply synchronize the data. Because of the backups, it will guarantee that even if a broker goes out of business, his data won't be lost.

![test1](https://snipboard.io/gmYbo6.jpg)


As you could observe in the image, each partition has a leader, which are represented by the yellow boxes, and each leader has a backup in other broker. In this way, if one broker fails the messages will be stored on other broker and the backup will become the leader of the partition in the other broker.


[Learn More](URL "https://medium.com/swlh/apache-kafka-what-is-and-how-it-works-e176ab31fcd5")


Let's watch this video: https://www.youtube.com/watch?v=Ch5VhJzaoaI 

---
## 2. Practice

### 2.1 Start zookeeper server
To start the zookeeper server open a Command Prompt and go to the path:
~~~
C:\kafka_2.13-3.2.3
~~~

Then run the following command to start the zookeeper server:
~~~
bin\windows\zookeeper-server-start.bat config\zookeeper.properties
~~~
![zookeeper00](https://snipboard.io/axWXqy.jpg)

The zookeeper server is now runnig locally!

### 2.2 Start kafka server (broker)
To start the kafka broker, open a new Command Prompt and go the the path: 
~~~
C:\kafka_2.13-3.2.3
~~~

Then run the following command to start the kafka broker:
~~~
bin\windows\kafka-server-start.bat config/server.properties
~~~
![broker00](https://snipboard.io/42XIdV.jpg)

The kafka server is now running locally too!

### 2.3 Create a topic
To create a new topic open other Command Prompt and go to the path:
~~~
C:\kafka_2.13-3.2.3\bin\windows
~~~

Then run the following command (**replace {Topic_Name} by the name of your topic**):
~~~
kafka-topics.bat --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic {Topic_Name}
~~~

To list all the topics contined at the broker, run the following command:
~~~
kafka-topics.bat --list --bootstrap-server localhost:9092
~~~
![topic00](https://snipboard.io/dj9YQe.jpg)

### 2.4 Producer from shell
To create a producer from the Command Promt, run the following command (**replace {Topic_Name} by the name of your topic**):
~~~
kafka-console-producer.bat --broker-list localhost:9092 --topic {Topic_Name}
~~~

Now you can send messages from the Command Prompt as a producer, but there is no consumer yet to recieve those messages.

### 2.5 Consumer from shell
To create a consumer from the Command Prompt, run the following command (**replace {Topic_Name} by the name of your topic**):
~~~
kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic {Topic_Name} 
~~~

Now you have a consumer to recieve messages!

It's time to test it, from the producer Command Prompt send a cumple of messages, you will see how those messages are recived by the consumer Command Prompt. 
![message_shell](https://snipboard.io/SDAozV.jpg)

### 2.6 Python Producer & Consumer

First we must close the Command Prompts of the poducer and the consumer by typing **Ctrl+c** in both terminals, then press **S** and you can close both terminals. 

Also, you can close the terminal we used previously to create the topic too. 

Open the Jupiter Notebooks *Producer.ipynb* and *Consumer.ipynb* and follow the instructions provided by the staff and in both notebooks. 

---
# Challege 1: Simulate a real-time chat
