FROM docker.elastic.co/beats/heartbeat:7.13.0-amd64

ENV setup.kibana.host=kibana:5601
ENV output.elasticsearch.hosts=["elasticsearch:9200"]

ADD ./heartbeat.yml /usr/share/heartbeat/heartbeat.yml

USER root

RUN chown root:heartbeat /usr/share/heartbeat/heartbeat.yml

USER heartbeat

