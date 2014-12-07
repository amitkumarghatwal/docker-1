# GlassFish 4.1 Docker image

This is a Dockerfile for [GlassFish Open Source Edition](http://www.glassfish.org) for version 4.1. The purpose of this Docker container is to facilitate the setup of development and integration testing environments for developers.

## How to Build

1. Checkout the GitHub glassfish/dockerfiles repository

		$ git checkout git@github.com:glassfish/docker.git glassfish-docker
		$ cd glassfish-docker

2. [Download](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) and drop the Oracle JDK 8u25 RPM 64bit file **jdk-8u25-linux-x64.rpm** in this folder

                Linux x64       135.6 MB        jdk-8u25-linux-x64.rpm

3. Execute the build script as root

		$ sudo sh build.sh

## Default Username and Password
Username: admin
Password: glassfish

## Booting up GlassFish on Docker

Along with the Dockerfile, one script is also provided to help you run GlassFish easily. To boot GlassFish, execute

		$ sudo sh dockGlassFish.sh

This script will automagically start default **domain1** and bind ports 4848 and 8080 to the host server. Log will be supressed, and the container will be daemonized. If you want to run GlassFish with ports binded to host, with log files on STDOUT, run the following command:

		$ sudo docker run -ti -p 4848:4848 -p 8080:8080 glassfish/javaee /opt/glassfish/glassfish4/bin/asadmin start-domain --verbose=true

## Deploying Java EE Applications

You can use the GlassFish Maven Plugin or the Web Console to deploy applications to the remote servers running on Docker containers.

## Dockerfile Source
All source is on the [glassfish/dockerfiles GitHub repository](https://github.com/glassfish/dockerfiles).

If you find any issues, please report through the [GitHub Issues page](https://github.com/glassfish/dockerfiles/issues).

## License
For the scripts and files hosted in the GitHub [glassfish/dockerfiles](https://github.com/glassfish/dockerfiles/) repository required to build the Docker image are, unless otherwise noted, released under the Common Development and Distribution License (CDDL) 1.0 and GNU Public License 2.0 licenses.

