# set pools replicasize to 1
## change pools replica size 
```bash
$ sudo ceph osd pool set <poolname> size <num-replicas>
```
## change pool replica size to 1
- its disabled by default
```bash
Error EPERM: configuring pool size as 1 is disabled by default.
```
- to change it should set mon_allow_pool_size_one to TRUE and reset monitor service
```bash
$ sudo ceph config get mon mon_allow_pool_size_one
$ sudo ceph config set mon mon_allow_pool_size_one true
# then reset mon service
$ sudo ceph orch reconfig mon
$ sudo ceph osd pool set **<POOL NAME>** size 1 --yes-i-really-mean-it
```