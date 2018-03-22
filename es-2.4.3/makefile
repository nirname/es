default: cluster

refresh: stop clean

node:
	docker-compose -f es-node.yml up

cluster:
	docker-compose -f es-cluster.yml up

stop:
	docker-compose -f es-cluster.yml down
	docker-compose -f es-node.yml down

check:
	curl http://127.0.0.1:9200/_cat/health

.PHONY: clean

clean:
	docker images elasticsearch -q | xargs -I{} docker rmi -f {}
	docker images docker.elastic.co/elasticsearch/elasticsearch -q | xargs -I{} docker rmi -f {}
	docker images -f dangling=true -q | xargs -I{} docker rmi -f {}
	yes | docker-compose -f es-cluster.yml rm
	yes | docker-compose -f es-node.yml rm