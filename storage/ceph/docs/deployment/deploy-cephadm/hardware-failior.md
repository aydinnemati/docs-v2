# for osd disks failed do these steps
- befor do enething just make sure that osd disk is failed is out of cluster and after removed, cluster is operational and in healthy state.
- befor removing entirely osd from cluster should gathering needed data such as:
  * phisical disks serialnumber
  * disk path in os
  * if wal/db is seperated find path and name of db lvm and wal lvm

after doing these steps and got a healthy cluser, set noout and norebalance flags and shut node down for replacing disk
for more information see below pages:
> [OSD SAFE REMOVE](./osd-safe-remove.md)

> safe shutdown cluster nodes