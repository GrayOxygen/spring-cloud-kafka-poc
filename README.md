# example using spring-cloud-stream
This example uses spring-cloud-stream to produce and consume messages from Kafka, with partitioned topic.

# setup kafka multi broker
See [kafka quickstart](https://kafka.apache.org/quickstart#quickstart_multibroker).

Create two partitioned topics:
```sh
bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 3 --partitions 2 --topic test
```

```sh
bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 3 --partitions 4 --topic test4
```

# run with 2 partitions:
execute one producer in a console:
```sh
cd spring-stream-poc-producer/
./gradlew bootRun
```

execute first consumer in a different console:
```sh
cd spring-stream-poc-consumer/
./gradlew bootRun
```

execute second consumer in a different console:
```sh
cd spring-stream-poc-consumer/
./gradlew bootRun
```

# run with 4 partitions:
execute one producer in a console:
```sh
cd spring-stream-poc-producer/
SPRING_PROFILES_ACTIVE=four ./gradlew bootRun
```

execute first consumer in a different console:
```sh
cd spring-stream-poc-consumer/
SPRING_PROFILES_ACTIVE=four ./gradlew bootRun
```

execute second consumer in a different console:
```sh
cd spring-stream-poc-consumer/
SPRING_PROFILES_ACTIVE=four ./gradlew bootRun
```

execute third consumer in a different console:
```sh
cd spring-stream-poc-consumer/
SPRING_PROFILES_ACTIVE=four ./gradlew bootRun
```

execute fourth consumer in a different console:
```sh
cd spring-stream-poc-consumer/
SPRING_PROFILES_ACTIVE=four ./gradlew bootRun
```
