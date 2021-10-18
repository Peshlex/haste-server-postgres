# Build and deploy haste server

## The Hastebin project

URL: https://github.com/toptal/haste-server

## Desired configuration

A Hastebin server running with a PostgreSQL database.

## Build

Familiarize yourself with the project and how it works.

Create a Dockerfile in which only the Hastebin and PostgreSQL settings and customizations are present.
The reason is that we won't be running this in any other setup so we might as well remove the unused stuff..

## Run locally on Docker

Run the project locally to ensure that the image is built correctly and it's working with the additional configuration.
With and without docker-compose in order to see the benefit of docker-compose for local project bootstrap and development.

## Run lockally on Kubernetes

install some local Kubernetes distro minikube, kind(Kubernetes in Docker).
Create the appropriate manifests to replicate the local setup(Run Hastebin and Postgre).

## Create a CI/CD process to build

Create a pipeline which has to check:
- The validity of the Dockerfile.
- Build the Docker image.
- Push the image to the Nexus private Docker registry(https://inttools.musala.com/nexus)

To verify that it's working pull the Docker image from the private Docker registry and run the setup locally.
