SHELL = /bin/bash -o pipefail

include .env

ROOT_DIR = $(CURDIR)
DOCKER_IMAGE_DIR = $(ROOT_DIR)/image

rebuild-all: rebuild-mysql rebuild-gitea rebuild-jenkins

rebuild-mysql:
	cd $(ROOT_DIR) && docker-compose rm -sf "mysql" && docker-compose up -d --no-deps --build "mysql"

rebuild-gitea:
	cd $(ROOT_DIR) && docker-compose rm -sf "gitea" && docker-compose up -d --no-deps --build "gitea"

rebuild-gitlab:
	cd $(ROOT_DIR) && docker-compose rm -sf "gitlab" && docker-compose up -d --no-deps --build "gitlab"

rebuild-jenkins:
	cd $(ROOT_DIR) && docker-compose rm -sf "jenkins" && docker-compose up -d --no-deps --build "jenkins"
