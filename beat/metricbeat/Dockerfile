FROM docker.elastic.co/beats/metricbeat:7.13.0-amd64

ADD ./metricbeat.yml /usr/share/metricbeat/metricbeat.yml

USER root

RUN chown root:metricbeat /usr/share/metricbeat/metricbeat.yml && chmod go-w /usr/share/metricbeat/metricbeat.yml

USER metricbeat
