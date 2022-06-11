# finding disks related to osds
See [ubuntu.com](https://ubuntu.com/ceph/docs/replacing-osd-disks)

```bash
$ sudo pvs
```
```bash
$ sudo lsblk -i -o NAME,FSTYPE
```


# finding osd disk name on os
1. osd config path (cat /var/lib/ceph/751fdb18-e648-11ec-b5ab-110e9bfd061c/osd.{{OSD.ID}}/fsid)
- get osd fsid, should be like
```bash
f4723652-c643-4622-802e-7b4713c2819e
```
2. then keep first part number and find disk by command below
```bash
sudo lsblk  | grep { first part of fsid} -B 1
```