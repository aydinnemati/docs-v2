# Test 1
## ceph quincy - taking out 3 OSD's (recovery time)
- ### started 18:30
- ### DEFAULT RECOVERY PRIORITY
- ### REMOVED 4 OSDs

```bash
  cluster:
    id:     4104ff12-db43-11ec-9817-a5cfe4d89d2f
    health: HEALTH_WARN
            1 failed cephadm daemon(s)
            Reduced data availability: 2 pgs inactive
            Degraded data redundancy: 1474602/15985443 objects degraded (9.225%), 15 pgs degraded, 13 pgs undersized
 
  services:
    mon: 3 daemons, quorum lff11-mon-01,sff13-mon-02,sff17-mon-03 (age 17m)
    mgr: lff11-mon-01.hhruvs(active, since 37m), standbys: sff13-mon-02.hxncqu, sff17-mon-03.inzpyi
    mds: 1/1 daemons up, 4 standby
    osd: 40 osds: 40 up (since 7m), 40 in (since 7m); 21 remapped pgs
 
  data:
    volumes: 1/1 healthy
    pools:   3 pools, 65 pgs
    objects: 5.33M objects, 254 MiB
    usage:   1.4 TiB used, 33 TiB / 34 TiB avail
    pgs:     3.077% pgs not active
             1474602/15985443 objects degraded (9.225%)
             929079/15985443 objects misplaced (5.812%)
             44 active+clean
             13 active+undersized+degraded+remapped+backfilling
             6  active+remapped+backfilling
             2  undersized+degraded+remapped+backfilling+peered
 
  io:
    recovery: 80 B/s, 24 keys/s, 23 objects/s
 

```

### 19:00
```bash
  cluster:
    id:     4104ff12-db43-11ec-9817-a5cfe4d89d2f
    health: HEALTH_WARN
            Failed to apply 1 service(s): osd.sff14-osd-03_wal_db_seperated
            1 failed cephadm daemon(s)
            Reduced data availability: 2 pgs inactive
            Degraded data redundancy: 1440776/15985443 objects degraded (9.013%), 15 pgs degraded, 15 pgs undersized
 
  services:
    mon: 3 daemons, quorum lff11-mon-01,sff13-mon-02,sff17-mon-03 (age 44m)
    mgr: lff11-mon-01.hhruvs(active, since 65m), standbys: sff13-mon-02.hxncqu, sff17-mon-03.inzpyi
    mds: 1/1 daemons up, 4 standby
    osd: 40 osds: 40 up (since 35m), 40 in (since 35m); 21 remapped pgs
 
  data:
    volumes: 1/1 healthy
    pools:   3 pools, 65 pgs
    objects: 5.33M objects, 254 MiB
    usage:   1.4 TiB used, 33 TiB / 34 TiB avail
    pgs:     3.077% pgs not active
             1440776/15985443 objects degraded (9.013%)
             912839/15985443 objects misplaced (5.710%)
             44 active+clean
             13 active+undersized+degraded+remapped+backfilling
             6  active+remapped+backfilling
             2  undersized+degraded+remapped+backfilling+peered
 
  io:
    recovery: 111 B/s, 14 keys/s, 26 objects/s

```

- ### full RECOVERY PRIORITY
> - all 20 and sleep 0
### 21:15
```bash
  cluster:
    id:     4104ff12-db43-11ec-9817-a5cfe4d89d2f
    health: HEALTH_WARN
            Failed to apply 1 service(s): osd.sff14-osd-03_wal_db_seperated
            1 failed cephadm daemon(s)
            Reduced data availability: 1 pg inactive
            Degraded data redundancy: 1122463/15985443 objects degraded (7.022%), 8 pgs degraded, 8 pgs undersized
 
  services:
    mon: 3 daemons, quorum lff11-mon-01,sff13-mon-02,sff17-mon-03 (age 2h)
    mgr: lff11-mon-01.hhruvs(active, since 3h), standbys: sff13-mon-02.hxncqu, sff17-mon-03.inzpyi
    mds: 1/1 daemons up, 4 standby
    osd: 40 osds: 40 up (since 2h), 40 in (since 2h); 12 remapped pgs
 
  data:
    volumes: 1/1 healthy
    pools:   3 pools, 65 pgs
    objects: 5.33M objects, 254 MiB
    usage:   1.4 TiB used, 33 TiB / 34 TiB avail
    pgs:     1.538% pgs not active
             1122463/15985443 objects degraded (7.022%)
             732113/15985443 objects misplaced (4.580%)
             53 active+clean
             7  active+undersized+degraded+remapped+backfilling
             4  active+remapped+backfilling
             1  undersized+degraded+remapped+backfilling+peered
 
  io:
    recovery: 0 B/s, 40 keys/s, 39 objects/s
```

### 09:00

```bash
  cluster:
    id:     4104ff12-db43-11ec-9817-a5cfe4d89d2f
    health: HEALTH_WARN
            Failed to apply 1 service(s): osd.sff14-osd-03_wal_db_seperated
            1 failed cephadm daemon(s)
            Degraded data redundancy: 147817/15985443 objects degraded (0.925%), 2 pgs degraded, 2 pgs undersized
 
  services:
    mon: 3 daemons, quorum lff11-mon-01,sff13-mon-02,sff17-mon-03 (age 14h)
    mgr: lff11-mon-01.hhruvs(active, since 15h), standbys: sff13-mon-02.hxncqu, sff17-mon-03.inzpyi
    mds: 1/1 daemons up, 4 standby
    osd: 40 osds: 40 up (since 14h), 40 in (since 14h); 2 remapped pgs
 
  data:
    volumes: 1/1 healthy
    pools:   3 pools, 65 pgs
    objects: 5.33M objects, 254 MiB
    usage:   1.4 TiB used, 33 TiB / 34 TiB avail
    pgs:     147817/15985443 objects degraded (0.925%)
             21000/15985443 objects misplaced (0.131%)
             63 active+clean
             2  active+undersized+degraded+remapped+backfilling
 
  io:
    recovery: 0 B/s, 1 keys/s, 1 objects/s

```