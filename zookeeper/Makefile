docker_img_name = zk-alpine
docker_version = 0.1
docker_container_name = zookeeper

docker-build:
	docker build -t $(docker_img_name):$(docker_version) -t $(docker_img_name):latest .

docker-run:
	docker run -d --name $(docker_container_name) -p 2181:2181 --restart=always zk-alpine

docker-stop:
	docker exec $(docker_container_name) /bin/bash -c "/mnt/apache-zookeeper-3.6.1-bin/bin/zkServer.sh stop"
	docker stop $(docker_container_name)
