# Python OpenCV Docker Image

This repository contains the Dockerfile and supporting files for building a Docker image with Python and OpenCV. The image is customizable with different versions of OpenCV and supports Alpine Linux as the base image.

## Prerequisites

- Docker installed on your machine.
- Basic understanding of Docker commands and Makefiles.

## Configuration

Two variables can be customized to build the image:

- `CV`: Specifies the OpenCV version to install. Default is `4.9.0`.
- `DIST`: Specifies the base distribution. Currently, only `alpine` is supported.

Example of setting variables:

```bash
make build CV=4.5.1 DIST=alpine
```

## Makefile Targets

### `run`

Executes the `build`, `test`, `login`, and `push` targets sequentially. This is a convenient way to build, test, and push the image with a single command.

### `build`

Builds the Docker image with the specified OpenCV version and base distribution. The image is tagged with the version and distribution for easy identification.

### `push`

Pushes the built image to the Docker repository specified by `ORG` and `REPO`. Requires authentication with the Docker registry.

### `latest`

Pulls the latest build for the specified OpenCV version and distribution, tags it as `latest`, and pushes this latest tag to the Docker repository. This is useful for keeping a `latest` version that tracks with your specific OpenCV and distribution choice.

### `test`

Runs a container using the built image to execute a test script. This is useful for verifying that the OpenCV installation within the container works as expected with your Python code.

### `save`

Saves the Docker image as a `.tar.gz` file. This is useful for archiving or transferring the image without using a Docker registry.

## Using the Makefile

To use the Makefile, navigate to the directory containing the Makefile and execute the desired target. For example, to build the image, run:

```bash
make build
```

To push the image to your Docker registry, ensure you are logged in to Docker and then run:

```bash
make push
```

## Contribution

Contributions are welcome. Please open an issue or submit a pull request for any improvements or bug fixes.

## License

Specify your license here.
