Задача 1

Ответ:

https://hub.docker.com/repository/docker/andrewchikin/05_virt_03_docker

docker run -d -p 8080:80 andrewchikin/05_virt_03_docker
Открыть в браузере http://localhost:8080/



Задача 2

Ответ:

Высоконагруженное монолитное java веб-приложение; 
Целесообразно использовать виртуальные или физические машины, монолитное приложение обычно тяжеловесно, имеет более длительное время запуска, выполняет несколько процессов, имеет зависимости которые следует учитывать при проектировании других контейнеров.

Nodejs веб-приложение; 
Docker. Простота развертывания, легковесность и масштабирование.

Мобильное приложение c версиями для Android и iOS; 
Не уверен что docker является здесь целевым, есть решения для организации сборки мобильных приложений (apk, deb, ipa), преимущества docker - развертывания, легковесность и масштабирование.

Шина данных на базе Apache Kafka; 
Docker, есть готовые образы для apache kafka, изолированность приложений, легкий откат на поздние версии в случае обнаружения багов

Elasticsearch кластер для реализации логирования продуктивного веб-приложения - три ноды elasticsearch, два logstash и две ноды kibana; 
Docker, Elasticsearch доступен для установки как образ docker, проще удалять логи, удобнее при кластеризации - меньше времени на запуск контейнеров.

Мониторинг-стек на базе Prometheus и Grafana; 
Docker. Есть готовые образы, приложения не хранят данные, что удобно при контейниризации, удобно масштабировать и быстро разворачивать.

MongoDB, как основное хранилище данных для java-приложения; 
Физическая машина как надежное, отказоустойчивое решение.

Gitlab сервер для реализации CI/CD процессов и приватный (закрытый) Docker Registry. 
Могут быть применены все варианты, в зависимости от наличия соответствующих ресурсов. Но для большей изолированности лучше использовать docker.



Задача 3

Ответ:
На мак приходиться писать полный путь к папке data - /Users/data

docker run -v /Users/data:/data --name centos_andrewchikin -d -t centos
docker run -v /Users/data:/data --name debian_andrewchikin -d -t debian

docker exec centos_andrewchikin /bin/bash -c "echo message_test>/data/readme.md"

Создал файл readme_host.md и добавил туда текст: message_test_by_host

Листинг и содержание файлов в /data второго контейнера контейнера.
Подключаемся во второй контейнер
r2d2@MacBook-Pro-Andrew data % docker exec -it debian_andrewchikin /bin/bash

root@1bb64b8e6b0c:/# cd /data
root@1bb64b8e6b0c:/data# ls -l
total 8
-rw-r--r-- 1 root root 13 Jul 11 18:47 readme.md
-rw-r--r-- 1 root root 20 Jul 11 18:50 readme_host.md

