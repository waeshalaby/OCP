FROM registry.access.redhat.com/openshift3/jenkins-agent-maven-35-rhel7

USER root

COPY settings.xml /opt/rh/rh-maven33/root/etc/maven/settings.xml
COPY settings.xml /home/jenkins/.m2/settings.xml
ADD  settings.xml $HOME/.m2

RUN chown -R 1001:0 $HOME && \
    chmod -R g+rw $HOME
    
