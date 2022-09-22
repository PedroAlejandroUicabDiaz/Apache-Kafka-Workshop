# Windows Installation <img src="https://upload.wikimedia.org/wikipedia/commons/c/c7/Windows_logo_-_2012.png" width="25" height="25">

---
## 1. Java SE Installation

### 1.1 Verify if Java SE is already installed
To can run Apache Kafka it is important to verify that our computer already have installed Java. To do it, open a new Command Prompt and run the following command:
~~~
java -version 
~~~

If you don't have Java installed, this error will appear you:
![Java00](https://snipboard.io/ZGmt5F.jpg)

### 1.2 Download & install Java SE
To dowload the latest version of Java [click here](https://www.java.com/en/download/).
![Java01](https://snipboard.io/L75Jty.jpg)

Once you have the Java installer, run it as administrator and follow the installation gide. Clic on **install button**, and wait until Java is installed in your PC. 
![Java01](https://snipboard.io/sXVBxi.jpg)

When Java is installed in your PC, clic on **close button**.
![Java02](https://snipboard.io/IwPfWT.jpg)

Now open new Command Prompt and run again:
~~~
java -version 
~~~

This should appear in your Command Prompt:
![Java03](https://snipboard.io/y1SmgJ.jpg)

---
## 2. Kafka Installation

### 2.1 Download Apache Kafka
Now it's time install Apache Kafka. Download the [latest version](https://kafka.apache.org/downloads) of Kafka (the file enclosed in red).
![Kafka00](https://snipboard.io/KJ8TY4.jpg)

Then, unzip the file and move it to the root folder of your computer.This must be the path in your Command Prompt:
~~~
C:\kafka_2.13-3.2.3
~~~
![Kafka01](https://snipboard.io/s29q7n.jpg)

### 2.2 Adjusting details
To keep everything kafka related file inside the *kafka_2.13-3.2.3* folder, go to the **config** folder, this is the path:
~~~
C:\kafka_2.13-3.2.3\config
~~~

#### 2.2.1 server.properties file
Open the **server.properties** file in your Notepad. Then searh for the section **Log Baiscs** and change: 
~~~
log.dirs=/tmp/kafka-logs
~~~
by:
~~~
log.dirs=/kafka_2.13-3.2.3/kafka-logs
~~~
and save the changes in the *server.properties* file.
![Kafka02](https://snipboard.io/N5HKVQ.jpg)

#### 2.2.2 zookeeper.properties file
Open the **zookeeper.properties** file in your Notepad, and change:
~~~
dataDir=/tmp/zookeeper
~~~
by:
~~~
dataDir=C:/kafka_2.13-3.2.3/zookeeper
~~~
and save the changes in the *zookeeper.properties* file.
![Kafka02](https://snipboard.io/mpi3nj.jpg)

---
## 3. Module kafka-python Instalation

### 3.1 kafka-python with pip
Open Anaconda Navigator, launch Jupyter Notebook and in a Python 3 notebook run in a cell the following command:
~~~
!pip install kafka-python
~~~
![Modules00](https://snipboard.io/PCHQYV.jpg)


### 3.2 kafka-python with conda
Open Anaconda Prompt and run the following conda command:
~~~
conda install -c conda-forge kafka-python
~~~
![Modules01](https://snipboard.io/NXBHG9.jpg)

## MacOS Installation <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/ab/Icon-Mac.svg/2048px-Icon-Mac.svg.png" width="25" height="25">

## Java Installation es lo mismo que en windows. Descargas directo de la página de Java.
![GotoJava](https://snipboard.io/kbed31.jpg)


### 2 Kafka installation
#### 2.1 Download Apache Kafka

Click on the following link where is located the archive:
https://www.apache.org/dyn/closer.cgi?path=/kafka/3.2.1/kafka_2.13-3.2.1.tgz

![Kafka01](https://snipboard.io/gRH2FV.jpg)


Copy the link

* In case that you don't have homebrew installed, use the following command:
~~~
$ brew ins/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
~~~

Execute the following command to install wget
~~~
$ brew install wget 
~~~

Now we use the following command to install the kafka:
~~~
$ wget (link that you copy before)
~~~

Once that is downloaded execute the following command:
~~~
$ tar -xvzf kafka_2.13-3.2.1.tgz 
~~~

Open the folder "kafka_2.13-3.2.1"
~~~
$ cd kafka_2.13-3.2.1
~~~

#### 2.2 zookeeper and kafka configuration

In order to make the communication we need to modify the configuration in kafka and the zookeeper. Lets modify it.
~~~
$ cd config/
$ vim server.properties
~~~

Once that you are inside the config locate the line where it says "advertised.listeners", it should be in a comment.
![Kafka02](https://snipboard.io/qPw7Kj.jpg)
We are going to change the text for:
~~~
adversited.listeners=PLAINTEXT://local.host:9092
~~~

In the same file locate the line where it says "zookeper.connect"
Replace it with:
~~~
zookeeper.connect=localhost:2181
~~~

Save the file using the button
":" and after pressing that button write "wq"

Go to the previous folder (kafka_2.13-3.2.1)
~~~
$cd .. 
~~~

Activate the zookeeper:
~~~
$ bin/zookeeper-server-start.sh config/zookeeper.properties
~~~

Open a new terminal or window terminal and lets run the kafka server.
~~~
$ cd kafka_2.13-3.2.1
$ JMX_PORT=8004 bin/kafka-server-start.sh config/server.properties 
~~~

So both servers are now connect.

![ServersUp](https://snipboard.io/Pa2bjZ.jpg) 
That is everything you need for the installation part!
:)
