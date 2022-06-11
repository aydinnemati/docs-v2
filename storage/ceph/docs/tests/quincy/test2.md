# test 2 - taking out osd's until cluster cant recover anymore
- cluster dont know osd's are down until read or write on them
```bash
   cluster:
    id:     4104ff12-db43-11ec-9817-a5cfe4d89d2f
    health: HEALTH_WARN
            Failed to apply 5 service(s): osd.sff10_wal_db_seperated,osd.sff12-osd-02_wal_db_seperated,osd.sff14-osd-03_wal_db_seperated,osd.sff15-osd-04_wal_db_seperated,osd.sff16-osd-05_wal_db_seperated
            15 failed cephadm daemon(s)
            failed to probe daemons or devices
            1 MDSs report slow metadata IOs
            1 MDSs report slow requests
            1/3 mons down, quorum sff13-mon-02,sff17-mon-03
            9 osds down
            2 hosts (15 osds) down
            Reduced data availability: 30 pgs inactive, 5 pgs down, 1 pg stale
            Degraded data redundancy: 8206413/19016655 objects degraded (43.154%), 56 pgs degraded, 56 pgs undersized
            38 slow ops, oldest one blocked for 478 sec, daemons [osd.17,osd.4] have slow ops.
 
  services:
    mon: 3 daemons, quorum sff13-mon-02,sff17-mon-03 (age 8m), out of quorum: lff11-mon-01
    mgr: sff13-mon-02.hxncqu(active, since 41h), standbys: sff17-mon-03.inzpyi
    mds: 1/1 daemons up, 2 standby
    osd: 40 osds: 20 up (since 8m), 29 in (since 11m); 25 remapped pgs
 
  data:
    volumes: 1/1 healthy
    pools:   3 pools, 65 pgs
    objects: 6.34M objects, 1.7 GiB
    usage:   1020 GiB used, 24 TiB / 25 TiB avail
    pgs:     46.154% pgs not active
             8206413/19016655 objects degraded (43.154%)
             23 active+undersized+degraded
             13 undersized+degraded+remapped+backfilling+peered
             12 undersized+degraded+peered
             8  active+undersized+degraded+remapped+backfilling
             5  down
             3  active+clean
             1  stale+active+clean
 
  io:
    recovery: 55 B/s, 35 keys/s, 25 objects/s

```
- after taking out 3 hosts (2 osd's and one monitor) just 5 pg's are down and 46.154% pgs are not active.
- cluster is not working...