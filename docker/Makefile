.PHONY: help
help:
	@echo "purge-containers: removes all containers from environments."
	@echo "purge-volumes: purges all system volumes."
	@echo "start-clean-environment: startializes a clear environment. REMOVES all data."
	@echo "start-environment: startializes environment."
	@echo "stop-environment: stops all containers"

.PHONY: purge-containers
purge-containers:
	docker container rm postgres
	docker container rm zookeeper
	docker container rm coordinator
	docker container rm broker
	docker container rm historical
	docker container rm middlemanager
	docker container rm router

.PHONY: purge-volumes
purge-volumes:
	docker volume prune -f

.PHONY: start-clean-environment
start-clean-environment: purge-volumes
	docker-compose up -d --force-recreate

.PHONY: start-environment
start-environment:
	docker-compose up -d

.PHONY: stop-environment
stop-environment:
	docker-compose down