.PHONY: help
help:
	@echo "purge-containers: removes all containers from environments."
	@echo "purge-volumes: purges all system volumes."
	@echo "start-environment-block: initializes the environment. Blocking call."
	@echo "stop-environment: stops all containers"

.PHONY: purge-containers
purge-containers:
	docker container rm schema_registry
	docker container rm middlemanager
	docker container rm router
	docker container rm druid-broker
	docker container rm historical
	docker container rm coordinator
	docker container rm superset_app
	docker container rm superset_worker_beat
	docker container rm superset_worker
	docker container rm superset_init
	docker container rm zookeeper
	docker container rm superset_cache
	docker container rm superset_db
	docker container rm postgres
	docker container rm kafka

.PHONY: purge-volumes
purge-volumes:
	docker volume prune -f

.PHONY: start-environment-block
start-environment-block:
	docker compose -f all-stack-docker-compose.yml up

.PHONY: stop-environment
stop-environment:
	docker compose -f all-stack-docker-compose.yml down
