# ruby-node-alpine

#### Simple Dockerfile for building Ruby + Node alpine images for custom versions.

Images available on [Docker Hub](https://hub.docker.com/repository/docker/thisismydesign/ruby-node-alpine) (currently on free tier with limited pulls, consider [supporting](https://github.com/sponsors/thisismydesign)).

```
docker run thisismydesign/ruby-node-alpine:3.0.2-16.13.0-alpine /bin/sh -c "ruby --version && node --version"
```

Available versions (defined in the [GitHub Actions workflow](.github/workflows/ci.yml)):
- Ruby: `[3.0.0, 3.0.1, 3.0.2, 3.0.3]`
- Node: `[16.13.0, 16.13.1]`

Versions are easily extendable by opening a PR or forking the repo and pushing images to your own registry.

## Usage

```sh
export RUBY_VERSION=3.0.3
export NODE_VERSION=16.13.0
docker build . --build-arg RUBY_VERSION=$RUBY_VERSION --build-arg NODE_VERSION=$NODE_VERSION --tag ruby-node-alpine:$RUBY_VERSION-$NODE_VERSION

docker run --rm ruby-node-alpine:$RUBY_VERSION-$NODE_VERSION /bin/sh -c "ruby --version && node --version"
```
