FROM docker.elastic.co/logstash/logstash-oss:6.2.4

WORKDIR /usr/share/logstash
RUN bin/logstash-plugin install logstash-input-jdbc

COPY conf/logstash.conf /etc/logstash/conf.d/logstash.conf
COPY conf/template.json /etc/logstash/conf.d/template.json

EXPOSE 5044:5044
CMD ["logstash", "-f", "/etc/logstash/conf.d/logstash.conf", "--config.reload.automatic", "--debug", "--verbose"]