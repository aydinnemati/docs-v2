# mount multiple ceph fs with arg **mds_namespace**
```bash
$ sudo mount -t ceph **<MON01>**,**<MON02>**:/ **<DIRECTORY TO MOUNT>**  -o name=admin,secret=**<SECRET>**,mds_namespace=**<FS-NAME>**
# example
$ sudo mount -t ceph 10.0.21.113,10.0.21.117:/ /ceph-fs02-r1/  -o name=admin,secret=AQBg8a5ipXAhDBAAP+gALHo5uf07mNf0vawH5w==,mds_namespace=fs02-r1

```

# mount ceph fs using kernel drivers
```bash
$ sudo mount -t ceph {device-string}:{path-to-mounted} {mount-point} -o {key-value-args} {other-args}
```
```bash
$ sudo mount -t ceph 192.168.0.1:6789,192.168.0.2:6789:/ /mnt/mycephfs -o name=foo,secret=AQATSKdNGBnwLhAAnNDKnH65FmVKpXZJVasUeQ==
```
```bash
$ sudo mount -t ceph :/ /mnt/mycephfs -o name=foo,secretfile=/etc/ceph/foo.secret
```
# unmounting cephFS
```bash
$ sudo umount /mnt/mycephfs
```
# persistent mounts
- to mount CephFS in your file systems table as a kernel driver, add the following to /etc/fstab
```bash
$ sudo [{ipaddress}:{port}]:/ {mount}/{mountpoint} ceph [name=username,secret=secretkey|secretfile=/path/to/secretfile],[{mount.options}]
```
- for example
```bash
:/     /mnt/ceph    ceph    name=admin,noatime,_netdev    0       2
```
## for more info see 
- [ceph.com](https://docs.ceph.com/en/octopus/cephfs/mount-using-kernel-driver/)


# mount ceph fs using kernel drivers [EXAMPLE]
```bash
$ sudo mount -t ceph 10.0.23.4:6789,10.0.23.6:6789:/ /data-ceph/  -o name=admin,secret=AQCl5uNgtTw4FBAA/NHD5ykDm77Ugz5lBa7jTQ==
```
```bash
$ sudo mount -t ceph 10.0.23.4:6789,10.0.23.6:6789:/test/path/to/mount /data-ceph/  -o name=*<client>*,secret=*<client_secret>* # mountes /test/path/to/mount OF CEPH 
FS TO /data-ceph ON DESTINATION

# example - fstab
# 10.0.21.113,10.0.21.117:/     /ceph/fs01-r3    ceph    name=admin,noatime,_netdev,noexec,nodiratime,secret=AQDEwbFiCqY8EBAAbvh2TuQ5VRUZV8+SaeBZ8g==,mds_namespace=fs01-r3    0       2
# 10.0.21.113,10.0.21.117:/     /ceph/fs02-r1    ceph    name=admin,noatime,_netdev,noexec,nodiratime,secret=AQDEwbFiCqY8EBAAbvh2TuQ5VRUZV8+SaeBZ8g==,mds_namespace=fs02-r1    0       2

```