# Steps

Make sure that Elasticsearch is storing data in local directory `/etc/es-data`.

Use below to create the directory first.

```bash
sudo mkdir -p /etc/es-data
```

Then run below command to get ES up and running. You will see a problem, please troubleshoot that.

```bash
docker run -d --name elasticsearch -p 9200:9200 -p 9300:9300 -v /etc/es-data:/usr/share/elasticsearch/data -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:7.4.1
```

Test whether Elasticsearch is running with below command

```bash
curl <your_servers_ip>:9200
```
