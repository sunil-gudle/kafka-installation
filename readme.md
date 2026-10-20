## Kafka Installation Repo

    docker.compose.yml file has command to run the install and run the kafka in docker

## Command Used

To run the docker image
- cd C:\Users\<Name>\IdeaProjects\kafka-installation
To Start:
- docker compose up -d
Check it:
- docker compose ps
- docker logs -f kafka
Test it:
- docker exec -it kafka /opt/kafka/bin/kafka-topics.sh --bootstrap-server localhost:9092 --create --topic test-topic
--partitions 3 --replication-factor 1
- docker exec -it kafka /opt/kafka/bin/kafka-topics.sh --bootstrap-server localhost:9092 --list
Stop it:
- docker compose down # stop and remove container (data is lost)
- docker compose stop # just stop, keep the container

Terminal 1: consumer (listen)
- docker exec -it kafka /opt/kafka/bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test-topic --from-beginning

Terminal 2: producer (publish)
docker exec -it kafka /opt/kafka/bin/kafka-console-producer.sh --bootstrap-server localhost:9092 --topic test-topic

Type a line in Terminal 2 and press Enter. It appears in Terminal 1. Press Ctrl+C to exit either one.