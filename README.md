# EnterpriseApplicationLog
Enterprise Application Log with RabbitMQ, LogStash, ElasticSearch and Kibana

## Releases and Release Notes
[![Latest release](https://img.shields.io/github/release/luizcarlosfaria/EnterpriseApplicationLog.svg)](https://github.com/luizcarlosfaria/EnterpriseApplicationLog/releases/latest) 
[![GitHub Release Date](https://img.shields.io/github/release-date/luizcarlosfaria/EnterpriseApplicationLog.svg)](https://github.com/luizcarlosfaria/EnterpriseApplicationLog/releases/latest)

[All releases](https://github.com/luizcarlosfaria/EnterpriseApplicationLog/releases) 

## About

### RabbitMQ

Provide log queue to perform async log write instead synchronous direct call to ElasticSearch.

### ElasticSearch

Log and Metrics Store.

### LogStash

Process logs from RabbitMQ and send to ElasticSearch

### Kibana

Data Visualization for ElasticSearch

### MetricBeat

Metrics for:
* Docker
* RabbitMQ
* ElasticSearch

### HeartBeat

Uptime monitoring for:
* ElasticSearch
* Kibana
* ...

### APM - Application Performance Monitoring 

Monitoring your application (.NET , Java, Node.js, Django, Flask, Rails, Rack RUM - JS and Go) [see more](https://www.elastic.co/pt/apm)


## How to use

On Windows, set **COMPOSE_CONVERT_WINDOWS_PATHS=1** environment variable to solve issue reported on [issue #1829 at docker/for-win repo](https://github.com/docker/for-win/issues/1829):

* Bash: `export COMPOSE_CONVERT_WINDOWS_PATHS=1`
* Cmd: `set COMPOSE_CONVERT_WINDOWS_PATHS=1`
* PowerShell: `$Env:COMPOSE_CONVERT_WINDOWS_PATHS=1`

```
git clone https://github.com/luizcarlosfaria/EnterpriseApplicationLog.git
cd ./EnterpriseApplicationLog
docker-compose up
```

## Releases

I've complete abandon SemVer because this does not represent the semantic needs for versioning this stack.

### Products-7.13.0-Stack-4.0.0

Update stack from 7.8.0 to 7.13.0.

Adding APM

Adding HeartBeat (for uptime monitoring)

Adding RabbitMQ plugins

Configure Prometheus RabbitMQ integration to expose queue metrics.

### Products-7.8.0-Stack-3.0.0

Update stack from 6.7.0 to 7.8.0.

### Products-6.7.0-Stack-2.0.0

Update stack from 6.2.2 to 6.7.0 (Contribution of [@tbaragao](https://github.com/tbaragao) updating stack to 6.7.0. Thank you!)

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
- [Website / Blog](http://gago.io/)
- [YouTube](https://www.youtube.com/luizcarlosfaria/)
- [Facebook Page](https://www.facebook.com/ArquitetoDeSolucoes/)
- [Facebook Group](https://www.facebook.com/groups/arquiteturadotnet/)

All content still produced in PT-BR language. To request an english version, please send me a message on [twitter](https://twitter.com/luizcarlosfaria) or [email](mailto:luizcarlosfaria@gmail.com).
