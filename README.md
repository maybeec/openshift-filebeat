# Filebeat for OpenShift with non-priviledged containers

As the basic docker container given by elastic is running as root, I created a new container allowing to run properly as a non-priviledged container in OpenShift.

## Mount points
See https://www.elastic.co/guide/en/beats/filebeat/master/directory-layout.html (rpm installation)

. The location of the configuration: /etc/filebeat/filebeat.yml
. The location for persistent data files: /var/lib/filebeat
. The location for the logs created by Filebeat: /var/log/filebeat
