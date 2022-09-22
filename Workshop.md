# Workshop

---
## 1. 

---
## 2. 

Let's watch this video: https://www.youtube.com/watch?v=Ch5VhJzaoaI 

---
## 3. Practice

### 3.1 Start zookeeper server
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

### 3.2 Start kafka server (broker)
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

### 3.3 Create a topic
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

### 3.4 Producer from shell
To create a producer from the Command Promt, run the following command (**replace {Topic_Name} by the name of your topic**):
~~~
kafka-console-producer.bat --broker-list localhost:9092 --topic {Topic_Name}
~~~

Now you can send messages from the Command Prompt as a producer, but there is no consumer yet to recieve those messages.

### 3.5 Consumer from shell
To create a consumer from the Command Prompt, run the following command (**replace {Topic_Name} by the name of your topic**):
~~~
kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic {Topic_Name} 
~~~

Now you have a consumer to recieve messages!

It's time to test it, from the producer Command Prompt send a cumple of messages, you will see how those messages are recived by the consumer Command Prompt. 
![message_shell](https://snipboard.io/SDAozV.jpg)

### 3.6 Python Producer & Consumer

First we must close the Command Prompts of the poducer and the consumer by typing **Ctrl+c** in both terminals, then press **S** and you can close both terminals. 

Also, you can close the terminal we used previously to create the topic too. 

Open the Jupiter Notebooks *Producer.ipynb* and *Consumer.ipynb* and follow the instructions provided by the staff and in both notebooks. 

---
# Challege 1: Simulate a real-time chat
