# kafka_installation
[Download kafka](https://apache.claz.org/kafka/2.7.0/kafka_2.13-2.7.0.tgz) 

## To unzip the downloaded file:
* ```tar -xzf kafka_2.13-2.7.0.tgz```
* ```cd kafka_2.13-2.7.0 ```
## To run kafka:
 Open PowerShell in C:\kafka_2.13-2.7.0 folder.
 

 ### Different PowerShell windows will be used for each process mentioned below and keep all the windows open.

 * Window 1 - Run Zookeeper Service
* * ``` .\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties```
* Window 2 - Run Kafka Service 
* * ``` .\bin\windows\kafka-server-start.bat .\config\server.properties ```
* Window 3 : To create and display the topics created.
* * ```.\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --create --topic GD-Messages ```
* * ```.\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --list ```
* Window 4 - Run Kafka Producer: Type messages here.
* * ``` .\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic GD-Mssages ```
Now type your messages in this powershell window.

* Window 5 - Run Kafka Consumer: To display Messages.
* * ``` .\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic GD-Messages --from-beginning```
