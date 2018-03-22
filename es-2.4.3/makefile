start:
	docker-compose up

stop:
	docker-compose down

check:
	curl http://127.0.0.1:9200/_cat/health

# build:
# 	docker build --tag es:2.4.3 .

# bash:
# 	run --rm -it my-es-image /bin/bash

.PHONY: clean

clean:
	docker images elasticsearch:2.4.3 -q | xargs -I{} docker rmi -f {}
	docker images -f dangling=true -q | xargs -I{} docker rmi -f {}
	yes | docker-compose rm

# docker images es:2.4.3 -q | xargs -I{} docker rmi -f {}