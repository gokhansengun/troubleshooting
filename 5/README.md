# Steps

Run below command and try to get Elasticsearch up and running

```bash
docker run -d --name elasticsearch -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:7.4.1
```

Test whether Elasticsearch is running with below command

```bash
curl <your_servers_ip>:9200
```

Remove all the containers to cleanup

```bash
docker rm -f -v $(docker ps -aq)
```
