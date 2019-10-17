
DOCKER_CONTAINER_NAME := go-builder
DOCKER_IMAGE_USER := 242617
DOCKER_IMAGE_NAME := go-builder
DOCKER_IMAGE_TAG := 1.0.0
DOCKER_IMAGE := ${DOCKER_IMAGE_USER}/${DOCKER_IMAGE_NAME}:${DOCKER_IMAGE_TAG}

.PHONY: build
build:
	docker build \
		-t ${DOCKER_IMAGE} \
		.

.PHONY: test
test:
	docker run \
		--rm \
		-it \
		--network host \
		-v `pwd`:/root \
		-u 0 \
		--name ${DOCKER_CONTAINER_NAME}\
		${DOCKER_IMAGE}

.PHONY: save
save:
	docker save ${DOCKER_IMAGE} > ${DOCKER_IMAGE_NAME}-v${DOCKER_IMAGE_TAG}.tar

.PHONY: push
push:
	docker push ${DOCKER_IMAGE}