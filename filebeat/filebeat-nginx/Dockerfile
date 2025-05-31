FROM nginx:alpine

RUN apk add --no-cache bash curl tar

RUN curl -L -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-8.13.4-linux-x86_64.tar.gz && \
    tar xzvf filebeat-8.13.4-linux-x86_64.tar.gz && \
    mv filebeat-8.13.4-linux-x86_64/filebeat /usr/local/bin/ && \
    rm -rf filebeat-8.13.4-linux-x86_64*

COPY filebeat.yml /etc/filebeat/filebeat.yml

CMD ["sh", "-c", "/usr/local/bin/filebeat -e -c /etc/filebeat/filebeat.yml & nginx -g 'daemon off;'"]

