# Install Kafka using Docker
## Install Kafka and ZooKeeper
First you will need Kafka and Zookeeper, defined in docker-compose.yml, Make sure to edit the ports if either 2181 or 9092 aren’t available on your machine.

```
docker-compose -f docker-compose.yml up -d
```

## Checking Kafka Shell
Then execute shell in container **kafka** using following script
```
docker exec -it kafka /bin/sh
```
