<p align="center">
    <div align="center">
        <h1>Kafka compose</h1>
        <p>
            <b>Простой запуск <a href="https://kafka.apache.org/uses">Kafka</a> </b>
        </p>
    </div>
</p>


В `localhost:8080` будет kowl, где удобно смотреть все про kafka

На `localhost:9092` будет сама кафка


1. загрузить проект - git clone https://github.com/danilalukyanchenkoQA/kafka-compose.git
2. запустить докер контейнеры - docker-compose up -d
3. войти в консоль контейнера - docker exec -it 8c2a8fcaabb1195fe7b5993f14f8938780da9cdfa1075f67d8863e1817226ada bash (Айди контейнера кафки на порту 9092:9092)
4. создать топик kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic Test 
5. Отправить сообщение брокеру - echo "Hello World" | kafka-console-producer.sh --broker-list localhost:9092 --topic Test
6.Прочитать сообщение - kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic Test --from-beginning    (from-beginning  - флаг для того чтобы прочитать все сообщения из топика)




P.S. - Делать все вышеописанные действия в Shell консоли

