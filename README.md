# Install Kafka using Docker & Python 
## Install Kafka and ZooKeeper
First you will need Kafka and Zookeeper, defined in docker-compose.yml, Make sure to edit the ports it is either 2181 or 9092.
this will also automatically start the broker.
```
docker-compose -f docker-compose.yml up -d
```

## Creating Topics from Kafka Shell
Then execute shell in container **kafka** using following script
```
docker exec -it kafka /bin/sh
```
All Kafka shell scripts are located in /opt/kafka_<version>/bin 
```
cd /opt/kafka_<version>/bin
```
after navigated into bin then create the topics using cli named it **messages**
```
kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 2 --topic messages
```
Now the topics, continue to scripting in Python, actually for automation purpose we could also create topic from Python Script
Which is,
```
topic_list = []
new_topic = NewTopic(name="message", num_partitions= 2, replication_factor=1)
topic_list.append(new_topic)
admin_client.create_topics(new_topics=topic_list)
```

## Install Python
kafka-python==2.0.2
