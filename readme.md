## 启动

```sh
docker-compose up -d
```

## 导入movies数据

下载

```
$ wget http://files.grouplens.org/datasets/movielens/ml-25m.zip
$ unzip ml-25m.zip
```

导入

```sh
docker run --rm -it --network es_elastic -v "$(pwd)"/config/logstash.yml:/usr/share/logstash/config/logstash.yml -v "$(pwd)"/pipeline:/usr/share/logstash/pipeline -v "$(pwd)"/ml-25m:/data/ml-25m docker.elastic.co/logstash/logstash:7.8.1
```


## links 

* https://grouplens.org/datasets/movielens/