.PHONY: help
help:
	@echo "purge-environment: removes all containers from environment."
	@echo "init-clean-environment: initializes a clear environment. REMOVES all data."
	@echo "init-environment: initializes environment."
	@echo "stop-environment: stops all containers"

.PHONY: purge-environment
purge-environment:
	docker container rm postgres
	docker container rm zookeeper
	docker container rm coordinator
	docker container rm broker
	docker container rm historical
	docker container rm middlemanager
	docker container rm router

.PHONY: init-clean-environment
init-clean-environment:
	docker-compose up -d --force-recreate

.PHONY: init-environment
init-environment:
	docker-compose up -d

.PHONY: stop-environment
stop-environment:
	docker-compose down