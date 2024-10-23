docker network create elastic_network

docker pull docker.elastic.co/elasticsearch/elasticsearch:8.12.2


docker run --rm -it \
-v $(pwd):/usr/share/elasticsearch/config \
docker.elastic.co/elasticsearch/elasticsearch:8.12.2 \
/bin/bash

bin/elasticsearch-certutil cert --ca elastic-stack-ca.p12
elastic-stack-ca.p12


/usr/share/elasticsearch/bin/elasticsearch-certutil cert --ca /usr/share/elasticsearch/elastic-stack-ca.p12 --name es01 --dns es01,localhost --out /usr/share/elasticsearch/config/es01.p12
/usr/share/elasticsearch/bin/elasticsearch-certutil cert --ca /usr/share/elasticsearch/elastic-stack-ca.p12 --name es02 --dns es01,localhost --out /usr/share/elasticsearch/config/es02.p12
/usr/share/elasticsearch/bin/elasticsearch-certutil cert --ca /usr/share/elasticsearch/elastic-stack-ca.p12 --name es03 --dns es01,localhost --out /usr/share/elasticsearch/config/es03.p12


sudo docker cp 2e9312e45693:/usr/share/elasticsearch/config ./config


curl -X GET "http://192.168.1.46:9301/employeevalidateindex5ghjghjhgj/_search"
curl -X POST "localhost:9200/index_name/_search"