openshift-jee-sample
====================

A sample app to be deployed on openshift environments

Note: to build this repository with maven you must specify "-Popenshift", eg "mvn clean package -Popenshift"

https://docs.openshift.com/container-platform/3.11/dev_guide/dev_tutorials/binary_builds.html

mkdir mavenapp
cd mavenapp

FROM wildfly:latest
COPY ROOT.war /wildfly/standalone/deployments/ROOT.war
CMD  $STI_SCRIPTS_PATH/run


cat Dockerfile | oc new-build -D - --name mavenapp

