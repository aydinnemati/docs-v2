# MAAS CLI
- for login to maas cli use command below
```bash
# first should get an api-key
$ sudo maas apikey --username=admin > api-key-file
$ maas login *<USER NAME[admin]>* http://localhost:5240/MAAS/api/2.0/
```
# increase maas node timeout 30 minutes
```bash
$ maas admin maas set-config name=node_timeout value=120
```