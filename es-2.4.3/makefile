start:
	docker-compose up

# stop:
# 	docker-compose down

build:
	docker build --tag es:2.4.3 .

bash:
	run --rm -it my-es-image /bin/bash

.PHONY: clean

clean:
	docker images es:2.4.3 -q | xargs -I{} docker rmi -f {}
	docker images -f dangling=true -q | xargs -I{} docker rmi -f {}
	docker-compose rm