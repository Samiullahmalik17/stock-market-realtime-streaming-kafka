# stock-market-realtime-streaming-kafka

## Introduction 
In this project, you will execute an End-To-End Data Engineering Project on Real-Time Stock Market Data using Kafka.

We are going to use different technologies such as Python, Amazon Web Services (AWS), Apache Kafka, Glue, Athena, and SQL.

## Technology Used
- Programming Language - Python
- MySQL
- Apache Kafka

# stockdata_streaming(commands and procedure)
-----------------------
java -version
sudo yum install java-1.8.0-openjdk
java -version
cd kafka_2.12-3.3.1

Start Zoo-keeper:
-------------------------------
bin/zookeeper-server-start.sh config/zookeeper.properties

Open another window to start kafka


Start Kafka-server:
----------------------------------------

cd kafka_2.12-3.3.1
bin/kafka-server-start.sh config/server.properties

It is pointing to private server , change server.properties so that it can run in public IP 


Create the topic:
-----------------------------
Duplicate the session & enter in a new console --
cd kafka_2.12-3.3.1
bin/kafka-topics.sh --create --topic demo_testing2 --bootstrap-server {Put the Public IP or localhost:9092} --replication-factor 1 --partitions 1


Start Producer:
--------------------------
bin/kafka-console-producer.sh --topic demo_testing2 --bootstrap-server {Put the Public IP or localhost:9092} 

Start Consumer:
-------------------------
Duplicate the session & enter in a new console --
cd kafka_2.12-3.3.1
bin/kafka-console-consumer.sh --topic demo_testing2 --bootstrap-server {Put the Public IP or localhost:9092}

After running zoo-keeper, kafka server, kafka producer and kafka consumer you can go to **producer.ipynb** run it and then **consumer.ipynb** .

Don't forget to change the configuration of your MySQL database after creating the schema according to the data being streamed through **indexProcessed.csv** the notebook will successfully dump the data in MySQL database.

If you need any sort of help you can connect me or email me at **samiullahmalk17@gmail.com**