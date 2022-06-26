# Ceph Tuning
- See [suse](https://documentation.suse.com/ses/6/html/ses-all/tuning-ceph.html)

# Obtaining Ceph Metrics
```bash
$ sudo ceph --admin-daemon /var/run/ceph/**<NODE FILE>** perf dump
# example
$ sudo ceph --admin-daemon /var/run/ceph/ceph-osd.104.asok perf dump
```
## or 
```bash
$ sudo ceph daemon **<DAEMON NAME>>** perf dump
# example
$ sudo ceph daemon osd.104 perf dump
```

# Making Tuning Persistent
- for persistent configuration should edit file on /etc/ceph/ceph.conf path whit below sections:
```bash
  [global]
  [osd]
  [mds]
  [mon]
  [mgr]
  [client]
```

# ceph logging
- it is possible to disable all logging to reduce latency in the various codepaths
> **WARNING**: This tuning should be used with caution and understanding that logging will need to be re-enabled should support be required. This implies that an incident would need to be reproduced after logging is re-enabled.



# BlueStore parameters

- Ceph is thin provisioned, including the Write-Ahead Log (WAL) files. By pre-extending the files for the WAL, time is saved by not having to engage the allocator. It also potentially reduces the likelihood of fragmentation of the WAL files. This likely only provides benefit during the early life of the cluster.

```bash
bluefs_preextend_wal_files=1
```

- BlueStore has the ability to perform buffered writes. Buffered writes enable populating the read cache during the write process. This setting, in effect, changes the BlueStore cache into a write-through cache.

```bash
bluestore_default_buffered_write = true
```

- To prevent writes to the WAL when using a fast device, such as SSD and NVMe, set:

```
prefer_deferred_size_ssd=0 (pre-deployment)
```