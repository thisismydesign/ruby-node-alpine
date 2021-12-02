# ruby-node-alpine

Simple Dockerfile for building custom Ruby + Node alpine images.

```sh
export RUBY_VERSION=3.0.3
export NODE_VERSION=16.13.0
docker build . --build-arg RUBY_VERSION=$RUBY_VERSION --build-arg NODE_VERSION=$NODE_VERSION --tag ruby-node-alpine-$RUBY_VERSION-$NODE_VERSION

docker run -i ruby-node-alpine-$RUBY_VERSION-$NODE_VERSION /bin/sh -c "ruby --version && node --version"
```
