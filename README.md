This is pfalcon's branch of LITE containerized LAVA setup.

Changes:
* Captures serial and generated configs for my boards.
* Some WIP changes for docker-compose setup (those which may be generally
  useful, are intended to be submitted upstream).

Read [correspondig doc section](https://collaborate.linaro.org/pages/viewpage.action?pageId=118293253#GettingStartedwithLAVA,Docker,andaFRDM-K64F:-(Semi)AutomatedContainerizedSetup)
to see how this is intended to be used).

The original README below.

-------

lite-lava-docker-compose
========================

This is a Linaro LITE customized fork of LAVA dockerized setup. Instructions
for it are available in the
[wiki](https://collaborate.linaro.org/pages/viewpage.action?pageId=118293253).

Below is the original README.

-------

docker-compose
==============

docker-compose file to setup an instance of **lava-server** and **lava-dispatcher**
from scratch. In this setup, every service will be running in a separate container.

Usage
=====

Requirements
------------

In order to use this docker-compose file, you need:

* docker.io
* docker-compose

You can install the dependencies using:

    apt install docker.io docker-compose

Installing
----------

You just need to fetch the sources:

    git clone https://git.lavasoftware.org/lava/pkg/docker-compose
    cd docker-compose

Using it
--------

In order to start the containers, run:

    docker-compose up

docker-compose will spawn a container for each services:

* PostgreSQL
* apache2
* gunicorn (aka lava-server-gunicorn)
* lava-master
* lava-logs
* lava-publisher

All the services will be connected to each others.

docker-compose will also create some volumes for:

* device dictionaries
* health-checks
* job outputs
* PostgreSQL data
