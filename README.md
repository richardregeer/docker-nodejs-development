# Docker nodejs web development
[![Build Status](https://travis-ci.org/richardregeer/docker-nodejs-development.svg?branch=master)](https://travis-ci.org/richardregeer/docker-nodejs-development)

This container can be used for doing all your Nodejs (web) development needs. Like running unit tests, linting, creating coverage reports and running your application with [Nodejs](https://nodejs.org/en/).

Docker images available for versions:
- [Node 6](./node-6)
- [Node 8](./node-8)
- [Node 9](./node-9)
- [Node 10](./node-10)
- [Node 11](./node-11)
- [Node 12](./node-12)
- [Node 13](./node-13)

## Installed software:
This image contains Nodejs. For more information about the installed tools see the web development base image [readme](https://github.com/richardregeer/docker-web-development).

## Verify installation
To verify the node installation:
```bash
docker run -it --rm richardregeer/web-development:node-<version> node -v
```

## How to use the container
Use a shared volume from a data container or host volume to share your code and start the program on the container.
Make sure the -rm option is used to destroy the container when it's finished.

Port 3000 is exposed and can be used for development. The default working directory of the image is /development.

```bash
# Start a node application in the container.
docker run -it --rm -v </path/to/your/code>:/development richardregeer/web-development:node-<version> node <your-application.js>
```
