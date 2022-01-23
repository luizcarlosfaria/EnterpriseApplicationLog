FROM docker.elastic.co/apm/apm-server-oss:7.13.0-amd64

ADD ./apm-server.yml /usr/share/apm-server/apm-server.yml

USER root

RUN chown root:apm-server /usr/share/apm-server/apm-server.yml && chmod go-w /usr/share/apm-server/apm-server.yml

USER apm-server
