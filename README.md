# Install Kafka using Docker
## Install Kafka and ZooKeeper
First you will need Kafka and Zookeeper, defined in docker-compose.yml, Make sure to edit the ports it is either 2181 or 9092.

```
docker-compose -f docker-compose.yml up -d
```

## Checking Kafka Shell
Then execute shell in container **kafka** using following script
```
docker exec -it kafka /bin/sh
```

# Create a Topic
All Kafka shell scripts are located in /opt/kafka_<version>/bin 
```
cd /opt/kafka_<version>/bin
```
kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 1 --topic messages
```
