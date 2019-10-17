# images

## go-builder

Alpine-based image for building Golang 1.13 applications.

| Command                        | Usage        |
|:-------------------------------|:-------------|
| Build image                    | `make build` |
| Test image (interactive login) | `make test`  |
| Save image to file             | `make save`  |
| Push image to hub              | `make push`  |

## docker-builder

Alpine-based image for building Docker containers.

| Command                        | Usage                                 |
|:-------------------------------|:--------------------------------------|
| Build image                    | `make build`                          |
| Bake image                     | `IMAGE_PATH=/path/to/image make bake` |
| Save image to file             | `make save`                           |
| Push image to hub              | `make push`                           |
