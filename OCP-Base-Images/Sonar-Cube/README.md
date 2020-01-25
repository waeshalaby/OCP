# SonarQube on OpenShift
This repo contains all of the resources required to build an OpenShift-specific
Docker image of SonarQube.

It is inspired by the upstream SonarQube Docker image:
https://github.com/SonarSource/docker-sonarqube

# Docker Hub

The SonarQube image is available on Docker Hub at: https://hub.docker.com/r/openshiftdemos/sonarqube/

# Deploy on OpenShift
You can do use the provided templates with an embedded or postgresql database to deploy SonarQube on 
OpenShift:

SonarQube with Embedded H2 Database:

    oc new-app -f sonarqube-template.yaml --param=SONARQUBE_VERSION=7.9

SonarQube with PostgreSQL Database:

    oc new-app -f sonarqube-postgresql-template.yaml --param=SONARQUBE_VERSION=7.9
#####//////////////////////////////////////////////#####
for DevOps Env: "Deployed on the DevOps OpenShift Cluster on SonarQube namespace"

use the following commands :
1. cat Dockerfile | oc new-build --name test-sonarqube --dockerfile='-'

2. oc start-build test-sonarqube --from-dir="." --follow

we created the postgres DB Pod from the image stream on the same namespace 
