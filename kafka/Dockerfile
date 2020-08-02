FROM alpine as kafka_build

# install Java dependency
RUN apk update && apk upgrade && apk add --no-cache tar bash openjdk11-jre

# copy zookeeper binary
COPY src/. /mnt/

#
WORKDIR /mnt

# unpack kafka binary
RUN tar -xzvf kafka_2.12-2.5.0.tgz

# move config
RUN mv server.properties kafka_2.12-2.5.0/config/server.properties

EXPOSE 9092

CMD [ "/mnt/kafka_2.12-2.5.0/bin/kafka-server-start.sh", "/mnt/kafka_2.12-2.5.0/config/server.properties"]
