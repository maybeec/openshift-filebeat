# Filebeat for OpenShift with non-priviledged containers

As the basic docker container given by elastic is running as root, I created a new container allowing to run properly as a non-priviledged container in OpenShift.

## Mount points
See https://www.elastic.co/guide/en/beats/filebeat/master/directory-layout.html (rpm installation)

1. The location of the configuration: /etc/filebeat/filebeat.yml
```
volumeMounts:
  - mountPath: /etc/filebeat/filebeat.yml
    name: filebeat-config
    readOnly: true
    subPath: filebeat.yml
```

2. The location for persistent data files: /var/lib/filebeat
```
volumeMounts:
  - mountPath: /var/lib/filebeat
    name: filebeatdata
```

3. The location for the logs created by Filebeat: /var/log/filebeat
```
volumeMounts:
  - mountPath: /var/log/filebeat
    name: filebeatlogs
```
