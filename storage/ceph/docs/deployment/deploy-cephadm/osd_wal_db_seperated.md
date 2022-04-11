# deploy osd with seperated wal and db
See [ceph.com](https://docs.ceph.com/en/pacific/rados/configuration/bluestore-config-ref/)


# getting started
1. create volume group for WALs and DBs
```bash
$ sudo vgcreate ceph-db-0 /dev/sdx

# example
$ sudo vgcreate ceph-sff10-ssd00 /dev/sdg
```

2. create logical volumes for WAL and DB
```bash
$ sudo lvcreate -L 50GB -n db-0 ceph-db-0
```
> WAL
```bash
$ sudo lvcreate -L 45GB -n ceph-sff10-wal00 ceph-sff10-ssd00
```
> DB
```bash
$ sudo lvcreate -L 35GB -n ceph-sff10-db00 ceph-sff10-ssd00
```

# **Deferred writes**
Unlike in filestore, where every write is written in its entirety to both the journal and then
finally to disk, in BlueStore, the data part of the write in most cases is written directly to the
block device. This removes the double-write penalty and, on pure spinning-disk OSDs,
dramatically improves performance and lowers SSD wear. However, as mentioned
previously, this double write has a positive side effect of decreasing write latency when the
spinning disks are combined with SSD journals. BlueStore can also use flash-based storage
devices to lower write latency by deferring writes, first writing data into the RocksDB WAL
and then later flushing these entries to disk. Unlike filestore, not every write is written into
the WAL; configuration parameters determine the I/O size cut-off as to what writes are
deferred. The configuration parameter is shown in the following code:
bluestore_prefer_deferred_size
This controls the size of I/Os that will be written to the WAL first. For spinning disks, this
defaults to 32 KB, and SSDs by default don't defer writes. If write latency is important and
your SSD is sufficiently fast, then by increasing this value, you can increase the size of I/Os
that you wish to defer to WAL.

# sample: 45 GB WAL - 35 GB DB

# deploy OSDs

## manually
```bash
$ sudo ceph-volume lvm create --bluestore --data ceph-block-0/block-0 --block.db ceph-db-0/db-0
```


## yaml file using service specs(using path)

```yaml
service_type: osd
service_id: osd_wal_db_seperated_sff-15
placement:
  hosts:
    - sff-14
data_devices:
  # limit: 9
  # all: true
  paths:
    - /dev/sdc
    - /dev/sdd
    - /dev/sde
    - /dev/sdf
    - /dev/sdg
    - /dev/sdj
    - /dev/sdi
    - /dev/sdk
    - /dev/sdl

db_devices:
  paths:
    - ceph-sff15-ssd00/ceph-sff15-db00
    - ceph-sff15-ssd00/ceph-sff15-db01
    - ceph-sff15-ssd00/ceph-sff15-db02
    - ceph-sff15-ssd00/ceph-sff15-db03
    - ceph-sff15-ssd00/ceph-sff15-db04
    - ceph-sff15-ssd00/ceph-sff15-db05
    - ceph-sff15-ssd00/ceph-sff15-db06
    - ceph-sff15-ssd00/ceph-sff15-db07
    - ceph-sff15-ssd00/ceph-sff15-db08

wal_devices:
  paths:
    - ceph-sff15-ssd00/ceph-sff15-wal00
    - ceph-sff15-ssd00/ceph-sff15-wal01
    - ceph-sff15-ssd00/ceph-sff15-wal02
    - ceph-sff15-ssd00/ceph-sff15-wal03
    - ceph-sff15-ssd00/ceph-sff15-wal04
    - ceph-sff15-ssd00/ceph-sff15-wal05
    - ceph-sff15-ssd00/ceph-sff15-wal06
    - ceph-sff15-ssd00/ceph-sff15-wal07
    - ceph-sff15-ssd00/ceph-sff15-wal08
```

# deploy
```bash
$ sudo ceph orch apply -i ./*<file_name>*
```
