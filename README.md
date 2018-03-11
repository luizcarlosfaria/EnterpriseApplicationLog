# EnterpriseApplicationLog
Enterprise Application Log with RabbitMQ, LogStash, ElasticSearch and Kibana

## Releases and Release Notes
[![Latest release](https://img.shields.io/github/release/docker-gallery/EnterpriseApplicationLog.svg)](https://github.com/docker-gallery/EnterpriseApplicationLog/releases/latest) 
[![GitHub Release Date](https://img.shields.io/github/release-date/docker-gallery/EnterpriseApplicationLog.svg)](https://github.com/docker-gallery/EnterpriseApplicationLog/releases/latest)

[All releases](https://github.com/docker-gallery/EnterpriseApplicationLog/releases) 

## How to use
```
git clone https://github.com/docker-gallery/EnterpriseApplicationLog.git
cd ./EnterpriseApplicationLog
docker-compose up
```
## Releases

I've complete abandon SemVer because this does not represent the semantic need for versioning a stack.


### Products-6.2.2-Stack-1.1.0

Adding beats (metricbeat) to monitoring Docker, RabbitMQ and ElasticSearch with premade dashboards. 

### Products-6.2.2-Stack-1.0.0

Upgrade to Elasticsearch 6.2.2, Logstash 6.2.2, Kibana 6.2.2 with new images provided on docker.elastic.co.

## Result

### RabbitMQ
- New and default *virtual host* ```EnterpriseLog``` will be created automatically
- Use **[http://localhost:15672/](http://localhost:15672/)** for management with **User**: ```logUser``` and **Password**: ```logPwd```

### ElasticSearch
- Will be used to storage Log content

### LogStash
- Are configurated to **create** ```ApplicationLog``` *queue* on ```EnterpriseLog``` *virtual host* and listen this queue
- Every message in ```EnterpriseLog/ApplicationLog``` will be send to ```ElasticSearch```

### Kibana
- Was configurated to read data from ```ElasticSearch```
- Use **[http://localhost:5601/](http://localhost:5601/)** for management Kibana without credentials

### Beats
- Monitoring and collecting metrics from ```Docker Daemon```, ```ElasticSearch``` and ```RabbitMQ```.
- Automatic setup some dashboards to show these metrics

# Enjoy!
more content like that you will see on:
- [Website / Blog](http://luizcarlosfaria.net/)
- [YouTube](https://www.youtube.com/luizcarlosfaria/)
- [Facebook Page](https://www.facebook.com/ArquitetoDeSolucoes/)
- [Facebook Group](https://www.facebook.com/groups/arquiteturadotnet/)

All content still produced in PT-BR language. To request an english version, please send me a message on [twitter](https://twitter.com/luizcarlosfaria) or [email](mailto:luizcarlosfaria@gmail.com).
