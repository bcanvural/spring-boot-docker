# Spring-boot-docker

Builds a spring boot app image and optionally pushes it to a public docker image repo

## How to run

* Build a docker image locally

```bash
  $ mvn clean install
```

* Build a docker image locally and push to docker repo:

```bash
  $ mvn clean install -P push
```
