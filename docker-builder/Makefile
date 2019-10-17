
DOCKER_CONTAINER_NAME := docker-builder
DOCKER_IMAGE_USER := 242617
DOCKER_IMAGE_NAME := docker-builder
DOCKER_IMAGE_TAG := 1.0.0
DOCKER_IMAGE := ${DOCKER_IMAGE_USER}/${DOCKER_IMAGE_NAME}:${DOCKER_IMAGE_TAG}

.PHONY: build
build:
	docker build \
		-t ${DOCKER_IMAGE} \
		.

.PHONY: bake
bake:
	docker run \
		--rm \
		-v ${IMAGE_PATH}:/root/image \
		-v /var/run/docker.sock:/var/run/docker.sock \
		--name ${DOCKER_CONTAINER_NAME} \
		${DOCKER_IMAGE}

.PHONY: save
save:
	docker save ${DOCKER_IMAGE} > ${DOCKER_IMAGE_NAME}-v${DOCKER_IMAGE_TAG}.tar

.PHONY: push
push:
	docker push ${DOCKER_IMAGE}