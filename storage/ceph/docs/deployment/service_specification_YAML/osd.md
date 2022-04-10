```yaml
service_type: osd
service_id: osd_using_paths
placement:
  hosts:
    - Node01
    - Node02
data_devices:
  paths:
    - /dev/sdb
db_devices:
  paths:
    - /dev/sdc
wal_devices:
  paths:
    - /dev/sdd
service_type: osd
service_id: sff-10-service-name
placement:
  hosts:
    - sff-10

data_devices:
  limit: 9 # limit how many disks are going to be an OSD
  all: true
```


```yaml
service_type: osd
service_id: osd_using_paths
placement:
  hosts:
    - Node01
    - Node02
data_devices:
  paths:
    - /dev/sdb
db_devices:
  paths:
    - /dev/sdc
wal_devices:
  paths:
    - /dev/sdd
```

