# edison-microservice
Common basis for some of otto.de's micro-services using Spring Boot.

## Status
[![Build Status](https://travis-ci.org/otto-de/edison-microservice.svg)](https://travis-ci.org/otto-de/edison-microservice)

[![Maven Central](https://maven-badges.herokuapp.com/maven-central/de.otto.edison/edison-service/badge.svg)](https://maven-badges.herokuapp.com/maven-central/de.otto.edison/edison-service)

[![Dependency Status](https://www.versioneye.com/user/projects/55ba6f016537620017001905/badge.svg?style=flat)](https://www.versioneye.com/user/projects/55ba6f016537620017001905)


## About
This project contains a number of independent libraries that may be used to create microservices on top of Spring Boot. The libraries are used in different projects at OTTO. It's purpose is to provide a common implementation for cross-cutting requirements like:
* Health checks that are used to tell the load balancer or mesos platform whether or not a service is healthy.
* A Status page/document that may be used to give information about the current state of the service. Status information may also include details about sub-components, background jobs like imports, and so on.
* A simple job handling library that is used to run asynchronous background jobs, which for example can be used to run data imports from other systems.
* An optional MongoDB-based implementation of a JobRepository
* Support for MongoDB-based repositories in case you do not like Spring Data
* Reporting of metrics to Graphite
* Logging of messages to Kafka queues
* Support for feature toggles based on the Togglz library

... plus all the features of [Spring Boot](http://projects.spring.io/spring-boot/).

## Examples

There are a few examples that may help you to start your first microservice based
on Edison and Spring Boot. Because Spring Boot itself has some complexity, it is
recommended to first read it's documentation before starting with Edison.

The examples can be started with gradle:

    gradle clean example-jobs:bootRun
    gradle clean example-metrics:bootRun
    gradle clean example-status:bootRun
