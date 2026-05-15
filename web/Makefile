include .env

.PHONY: up down build

up:
	docker compose -p micro-saas up -d --remove-orphans

down:
	docker compose -p micro-saas down

build:
	docker compose -p micro-saas build
