# docker_kafka_rabbitmq
消息队列
'''
docker pull rabbitmq
'''
'''
docker run -d --hostname my-rabbit --name rabbit -p 15672:15672 -p 5673:5672 rabbitmq
'''
'''
docker exec -it rabbitmq /bin/bash
'''
'''
rabbitmq-plugins enable rabbitmq_management
'''
'''
docker pull wurstmeister/zookeeper 
'''
'''
docker run -d --restart=always --log-driver json-file --log-opt max-size=100m --log-opt max-file=2  --name zookeeper -p 2181:2181 -v /etc/localtime:/etc/localtime wurstmeister/zookeeper
'''
'''
docker ps
'''
'''
docker pull wurstmeister/kafka
'''
'''
docker exec -it kafka ifconfig
'''
'''
docker run -d  --log-driver json-file --log-opt max-size=100m --log-opt max-file=2 --name kafka -p 9092:9092 -e KAFKA_BROKER_ID=0 -e KAFKA_ZOOKEEPER_CONNECT=【IP】:2181/kafka -e KAFKA_ADVERTISED_LISTENERS=PLAINTEXT://127.0.0.1:9092 -e KAFKA_LISTENERS=PLAINTEXT://127.0.0.1:9092 -v /etc/localtime:/etc/localtime wurstmeister/kafka
'''
'''
docker exec -it kafka /bin/bash
'''
'''
cd  /opt/kafka_2.13-2.8.1/bin
'''
'''
./kafka-topics.sh --create --topic test-kafka --bootstrap-server localhost:9092
'''
'''
./kafka-topics.sh --describe --topic test-kafka --bootstrap-server localhost:9092
'''
'''
./kafka-console-consumer.sh --topic test-kafka --from-beginning --bootstrap-server localhost:9092
'''
'''
./kafka-console-producer.sh --topic test-kafka --bootstrap-server localhost:9092
'''
