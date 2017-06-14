# This image is based off the latest Jenkins LTS
FROM jenkinsci/jenkins:lts-alpine

USER root

# Add the docker binary so running Docker commands from the master works nicely
RUN apk -U add docker

COPY target/plugins /usr/share/jenkins/ref/plugins/

RUN for f in /usr/share/jenkins/ref/plugins/*.hpi; do mv "$f" "${f%%hpi}jpi"; done

USER jenkins
