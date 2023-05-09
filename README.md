# Keycloak for the Feasibility Application

## Purpose
Both for backend and frontend development an instance of Keycloak is mandatory.
This project provides an easy way to start a Docker container running an instance of a Keycloak server with a suitable configuration for development.

**CAUTION** Setting up keycloak in your production environment requires you to take additional steps in order to secure your system.
Please see [the documentation over at keycloak.org](https://www.keycloak.org/server/configuration-production) for instructions

## Configuration

### Users

There are no users created in the default imported realm. You need to create the users on your own and assign
the respective roles to them. The roles however are already configured.

For development purposes, **and ONLY for development purposes**, there is a `feasibility-realm.json.dev` file that 
contains 3 predefined users. `admin`, `user` and `poweruser`, with pre-assigned roles (poweruser is assigned as user
_and_ poweruser).
If you want to use this, and are aware of what you are doing, simple rename the file `feasibility-realm.json.dev` to
`feasibility-realm.json`. Please note that you still have to log in as admin and assign credentials to those users.

### Clients

One client is preconfigured for you to use. Its client id is _feasibility-webapp_

## Run Docker container
```
docker-compose up -d 
```
## Test Keycloak

By default (as of the provided _docker-compose.yml_), port 8080 is mapped to port 8080 on the host system.

After starting a Keycloak container open a browser
```
http://localhost:8080/
```
login to Keycloak as admin
```
Administration Console >
```
