docker_img_name = kafka-alpine
docker_version = 0.2
docker_container_name = kafka

docker-build:
	docker build -t $(docker_img_name):$(docker_version) -t $(docker_img_name):latest .

docker-run:
	docker run -d \
		--name $(docker_container_name) \
		-p 9092:9092 \
		--link=zookeeper \
		--restart=always \
		$(docker_img_name)

docker-stop:
	docker exec $(docker_container_name) /bin/bash -c "/mnt/apache-zookeeper-3.6.1-bin/bin/zkServer.sh stop"
	docker stop $(docker_container_name)
