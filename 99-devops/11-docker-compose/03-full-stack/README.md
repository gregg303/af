# 03-full-stack

This is an example of a full stack integration between PingAccess, PingFederate and PingDirectory.

[docker-compose.yaml](https://raw.githubusercontent.com/pingidentity/pingidentity-devops-getting-started/master/11-docker-compose/03-full-stack/docker-compose.yaml)

## Getting started

Please refer to the [Docker Compose Overview](./) for details on how to start, stop, cleanup stacks.

To start the stack, from the directory this file is in run:

`docker-compose up -d`

Watch the directories initialize with:

`docker-compose logs -f`

To stand up multiple containers, run compose with the `--scale` argument:

`docker-compose up --scale pingdirectory=3 --pingfederate=2`

## Using the containers

Once you see that the containers are healthy in `docker ps`

* Go to [https://localhost:9031/OAuthPlayground](https://localhost:9031/OAuthPlayground)
* Click on `implicit` link
* Click on `Submit` button
* Log in with `user.0 / 2FederateM0re`

To see the PingFederate management console

* Go to [https://localhost:9999/pingfederate/app](https://localhost:9999/pingfederate/app)
* Log in with `Administrator / 2FederateM0re`

To see the PingAccess management console

* Go to [https://localhost:9000](https://localhost:9000)
* Log in with `Administrator / 2FederateM0re`
* Note: You will be asked to accept license agreement and change password

To see the PingCentral management console

* Go to [https://localhost:9022](https://localhost:9022)
* Log in with `Administrator / 2Federate`

To see the PingDirectory management console

* Go to [https://localhost:8443/console](https://localhost:8443/console)
* Log in with:
 server: pingdirectory 
 user: Administrator 
 password: 2FederateM0re

PingDirectory exposes LDAP traffic via an LDAPS port 1636.

* Navigate to [https://localhost:1636/dc=example,dc=com](https://localhost:1636/dc=example,dc=com)

## Cleaning up

To bring the stack down:

`docker-compose down`

