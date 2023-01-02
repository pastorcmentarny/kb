## **HONEST WARNING**
**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._ 


# KAFKA
Kafka is an event streaming platform.It is a tool to manage data movement at scale. Apache Kafka is a distributed streaming platform for publishing and subscribing, storing, and processing streaming data at scale and in real-time. 


The Kafka cluster stores streams of records in categories called topics.

Each record consists of a key, a value, and a timestamp.

## Kafka API
* The Producer API allows an application to publish a stream of records to one or more Kafka topics.
* The Consumer API allows an application to subscribe to one or more topics and process the stream of records produced to them.
* The Streams API allows an application to act as a stream processor, consuming an input stream from one or more topics and producing an output stream to one or more output topics, effectively transforming the input streams to output streams.
* The Connector API allows building and running reusable producers or consumers that connect Kafka topics to existing applications or data systems. For example, a connector to a relational database might capture every change to a table.

## TOPIC
* A topic is a category or feed name to which records are published. 
* Topics in Kafka are always multi-subscriber; that is, a topic can have 0, 1, many consumers that subscribe to the data written to it.
* Topic stores a time-ordered sequence of messages that share the same category.
* Each topic has to have a single partition. 

## PARTITION
* Partition is a physical representation of the topic as commit log stored on one or more brokers.  
* Each partition must fit entirely on one machine.
* Each partition is an ordered, immutable sequence of records that is continually appended to—a structured commit log. 
* Each partition is replicated across a configurable number of servers for fault tolerance.
* Each partition has one server which acts as the "leader" and zero or more servers which act as "followers". 

## RECORDS (known as MESSAGE)
* Records in the partitions are each assigned a sequential id number called the offset that uniquely identifies each record within the partition.
* Each message in Kafka contains Timestamp, ID,  Data content using a key-value pairs .
* The message offset is like placeholder. (It is like bookmark, last read place, in case of a Kafka topic, it is the last read message). 
  * value - the message content .
  * key is additional information in the message and can determine what partitions the message will be written to .
  * topic to which the Producer record will be sent.

## CONSUMER
* Consumer is responsible for read and process. it is a response for know what it read and not.
* If consumer didn't read, consumer establishing that its message offset is 0. as it read sequence it moves offset .
* This offset is controlled by the consumer.
* Consumer will advance its offset linearly as it reads records, but, in fact, since the position is controlled by the consumer it can consume records in any order it likes.
* The group.id is a string that uniquely identifies the group of consumer processes to which this consumer belongs.
* Each record published to a topic is delivered to one consumer instance within each subscribing consumer group. 
* Consumer instances can be in separate processes or on separate machines.
* The way consumption is implemented in Kafka is by dividing up the partitions in the log over the consumer instances so that each instance is the exclusive consumer of a "fair share" of partitions at any point in time. 

## PRODUCER
* The producer instances can only send Producer records that match the key and value serializers types it is configured with.
* The producer is responsible for choosing which record to assign to which partition within the topic.
* It writes to leader of the partition
* Best practice to catch send() method to surround with try/catch block  and use structured exception handling.
* The KafkaTemplate which wraps a Producer and provides convenience methods to send data to Kafka topics. 
* Kafka producer portioning strategy : 
    * Direct
    * Round-robin
    * Key mod-hash 
    * Custom

## CLUSTER
* Kafka is run as a cluster on one or more servers.
* Message Retention Policy. all published messages are retained by a Kafka cluster regardless is any consumer has consumed.
* The Kafka cluster retains all published records—whether or not they have been consumed—using a configurable retention period. 
* Each record consists of a key, a value, and a timestamp.
* The cluster is a grouping of multiple  Kafka  Broker.  This where zookeeper come in. 

## THE COMMIT LOG
* the Commit log it primary record of what happened . it continually appends events in the order in which they are received.
topic stores a time-ordered sequence of messages that share the same category.
* The commit log is useful of point of recovery (so you can redo all things that happened in the order in which they happened. It helps with replication and distribution that is useful for redundancy.

## GENERAL:
* Apache Kafka is a publish-subscribe messaging as a distributed commit log.
* Replication level set on topic level
* ISR = in sync replicas 
* Kafka do not automatically go out and search for replace peer. 
* if more message producer is needed, the solution is to add more and more producers.  if we need more message retention and redundancy, we add more and more brokers. if we need more metadata management facilities, we add more Zookeeper members. if we need more consumer then we use consumer groups that is collection of individual independent consumer working together.
* Event sourcing is an architectural style to maintaining an application’s state by capturing all changes as a sequence of time-ordered, immutable events.
* Offset behaviour, read != committed


## BROKER
* Broker is a place where Kafka keeps and maintain topics
* The broker is a node in the cluster.
* The topic is a logical name for 1 or more partition.
* Messages and Topics are kept in Broker


## KAFKA-SPRNG BOOT AND EMBEDDED KAFKA
* @EnableKafka annotation which enables the detection of the @KafkaListener annotation (and other annotation
* For sending messages we will be using the KafkaTemplate which wraps a Producer and provides convenience methods to send data to Kafka topics. 
* ‘BOOTSTRAP_SERVERS_CONFIG' property that specifies a list of host:port pairs used for establishing the initial connections to the Kafka cluster. 
* The Consumer is nothing more than a simple POJO that defines a method for receiving messages.
* The creation and configuration of the different Spring Beans needed for the Receiver POJO are grouped in the ReceiverConfig class.
* The kafkaListenerContainerFactory() is used by the @KafkaListenerannotation from the Receiver in order to configure a MessageListenerContainer. In order to create it, a ConsumerFactory and accompanying configuration Map is needed.
* GROUP_ID_CONFIG' which allows to identify the group this consumer belongs to.
* Consumers label themselves with a consumer group name, and each record published to a topic is delivered to one consumer instance within each subscribing consumer group.


## OTHER
* Fix duplication by set ''enable.idempotence''' to true.
* Messaging traditionally has two models: queuing and publish-subscribe.  In a queue, a pool of consumers may read from a server and each record goes to one of them; in publish-subscribe the record is broadcast to all consumers. Each of these two models has a strength and a weakness. The strength of queuing is that it allows you to divide up the processing of data over multiple consumer instances, which lets you scale your processing. Unfortunately, queues aren't multi-subscriber—once one process reads the data it's gone. Publish-subscribe allows you broadcast data to multiple processes, but has no way of scaling processing since every message goes to every subscriber. The consumer group concept in Kafka generalizes these two concepts. As with a queue the consumer group allows you to divide up processing over a collection of processes (the members of the consumer group). As with publish-subscribe, Kafka allows you to broadcast messages to multiple consumer groups.
*  Kafka as a kind of special purpose distributed filesystem dedicated to high-performance, low-latency commit log storage, replication, and propagation.
* Event Sourcing: An architecture style to maintain application’s state by capturing all changes as a sequence of time-ordereded immutable events.
* High throughput means how system distributes its load and efficiency  process  in parallel 
* @Configurationwhich indicates that the class can be used by the Spring IoC container as a source of bean definitions.
* Kafka is optimized for ability and latency. if you need durability, this can be achieved by replication. acks=1 good for latency acks=all good for durability
  in-sync replicas make sure you set a minimum number of replicas that must acknowledge 
  set retires as default is 0.
* acks - The number of acknowledgments the producer requires the leader to have received before considering a request complete. 
    * acks=0  producer will not wait for any acknowledgment from the server a
    * acks=1 the leader will write the record to its local log but will respond without awaiting full acknowledgement from all followers.
    * acks=-1 or acks=all his means the leader will wait for the full set of in-sync replicas to acknowledge the record. 
* Plan for moving data.
* Share schema to it can be correct for producer and consumer
* Think about exception handling through send to dead-queue or log
* You need monitoring Kafka: https://docs.confluent.io/current/kafka/monitoring.html
* Kafka is a database and provides ACID guarantees. However, it works differently than other databases. Kafka is also not replacing other databases. Rather, it's a complementary tool in your toolset.

# Kafka connector
READ THIS: https://opencredo.com/blogs/kafka-connect-source-connectors-a-detailed-guide-to-connecting-to-what-you-love/
Kafka Connect is a framework for connecting Kafka with external systems such as databases, key-value stores, search indexes, and file systems, using so-called Connectors.
value stores, search indexes, and file systems, using so-called Connectors.

Kafka Connectors are ready-to-use components, which can help us to import data from external systems into Kafka topics and export data from Kafka topics into external systems. 
A source connector collects data from a system. Source systems can be entire databases, streams tables, or message brokers. A source connector could also collect metrics from application servers into Kafka topics, making the data available for stream processing with low latency.

A sink connector delivers data from Kafka topics into other systems, which might be indexes such as Elasticsearch, batch systems such as Hadoop, or any kind of database.

We only have to make sure to insert a newline at the end, otherwise, the source connector won't consider the last line.

Transformations enable us to make simple and lightweight modifications to individual messages.

Kafka is a distributed streaming platform built on top of partitioned log files. 


## Avro

* Avro is a language independent, schema-based data serialization library. It uses a schema to perform serialization and deserialization. Moreover, Avro uses a JSON format to specify the data structure which makes it more powerful.
* Avro creates a data file where it keeps data along with schema in its metadata section. 
* Avro supports two types of data:
  * Primitive type: Avro supports all the primitive types. We use primitive type name to define a type of a given field. For example, a value which holds a String should be declared as {“type”: “string”} in Schema
  * Complex type: Avro supports six kinds of complex types: records, enums, arrays, maps, unions and fixed

