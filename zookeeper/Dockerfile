FROM alpine as zk_build

# install Java dependency
RUN apk update && apk upgrade && apk add --no-cache tar bash openjdk11-jre

# copy zookeeper binary
COPY src/. /mnt/

#
WORKDIR /mnt

# create zookeeper dataDir
RUN mkdir -p /var/lib/zookeeper

# unpack zookeeper binary
RUN tar -xzvf apache-zookeeper-3.6.1-bin.tar.gz

# move config
RUN mv zoo.cfg apache-zookeeper-3.6.1-bin/conf/
# replace zkServer.sh file
RUN mv zkServer.sh apache-zookeeper-3.6.1-bin/bin/

EXPOSE 2181 2888 3888 8080

CMD [ "/mnt/apache-zookeeper-3.6.1-bin/bin/zkServer.sh", "start-foreground"]
