# ~80% full cluster - recovery
> 6 hosts:
- 3 mons
- 3 osds(26 total 26 up, 26 in 8 near full)

## capacity
- 22 Tr
- ~80% full
- 1.5 m objects
- 545 pgs
- 62.9 pg per osd
- filled by 2G files

# take out an OSD
- lets see what happens

## BEFOR
```bash
sudo ceph -s
  cluster:
    id:     b5158006-fd1d-11ec-9283-279caa203eab
    health: HEALTH_WARN
            8 nearfull osd(s)
            3 pool(s) nearfull
 
  services:
    mon: 3 daemons, quorum sff13-mon02,sff17-mon03,lff11-mon01 (age 72m)
    mgr: lff11-mon01.wyprnu(active, since 21h), standbys: sff17-mon03.vfzejr, sff13-mon02.zmessl
    mds: 1/1 daemons up, 4 standby
    osd: 26 osds: 26 up (since 119m), 26 in (since 2h)
 
  data:
    volumes: 1/1 healthy
    pools:   3 pools, 545 pgs
    objects: 1.53M objects, 5.6 TiB
    usage:   18 TiB used, 4.4 TiB / 22 TiB avail
    pgs:     544 active+clean
             1   active+clean+scrubbing+deep
 
  io:
    client:   1.7 KiB/s rd, 500 MiB/s wr, 1 op/s rd, 2.26k op/s wr
```
## start
- 13:20
## 13:32
```bash
sudo ceph -s
  cluster:
    id:     b5158006-fd1d-11ec-9283-279caa203eab
    health: HEALTH_WARN
            1 failed cephadm daemon(s)
            2 backfillfull osd(s)
            10 nearfull osd(s)
            Low space hindering backfill (add storage if this doesn't resolve itself): 7 pgs backfill_toofull
            Degraded data redundancy: 163780/4642551 objects degraded (3.528%), 59 pgs degraded, 59 pgs undersized
            3 pool(s) backfillfull
            1 daemons have recently crashed
 
  services:
    mon: 3 daemons, quorum sff13-mon02,sff17-mon03,lff11-mon01 (age 90m)
    mgr: lff11-mon01.wyprnu(active, since 21h), standbys: sff17-mon03.vfzejr, sff13-mon02.zmessl
    mds: 1/1 daemons up, 4 standby
    osd: 26 osds: 25 up (since 11m), 25 in (since 79s); 59 remapped pgs
 
  data:
    volumes: 1/1 healthy
    pools:   3 pools, 545 pgs
    objects: 1.55M objects, 5.7 TiB
    usage:   17 TiB used, 3.9 TiB / 21 TiB avail
    pgs:     163780/4642551 objects degraded (3.528%)
             486 active+clean
             50  active+undersized+degraded+remapped+backfilling
             7   active+undersized+degraded+remapped+backfill_toofull
             2   active+recovering+undersized+degraded+remapped
 
  io:
    client:   1.5 KiB/s rd, 777 MiB/s wr, 1 op/s rd, 237 op/s wr
    recovery: 126 MiB/s, 3 keys/s, 34 objects/s
```
# taking second osd out
- 13:35

- 13:42
```bash
  cluster:
    id:     b5158006-fd1d-11ec-9283-279caa203eab
    health: HEALTH_WARN
            2 failed cephadm daemon(s)
            1 MDSs report slow metadata IOs
            6 backfillfull osd(s)
            1 osds down
            9 nearfull osd(s)
            Reduced data availability: 6 pgs inactive
            Low space hindering backfill (add storage if this doesn't resolve itself): 8 pgs backfill_toofull
            Degraded data redundancy: 316616/4737930 objects degraded (6.683%), 112 pgs degraded, 112 pgs undersized
            3 pool(s) backfillfull
            1 daemons have recently crashed
 
  services:
    mon: 3 daemons, quorum sff13-mon02,sff17-mon03,lff11-mon01 (age 100m)
    mgr: lff11-mon01.wyprnu(active, since 22h), standbys: sff17-mon03.vfzejr, sff13-mon02.zmessl
    mds: 1/1 daemons up, 4 standby
    osd: 26 osds: 24 up (since 6m), 25 in (since 10m); 59 remapped pgs
 
  data:
    volumes: 1/1 healthy
    pools:   3 pools, 545 pgs
    objects: 1.58M objects, 5.8 TiB
    usage:   18 TiB used, 3.5 TiB / 21 TiB avail
    pgs:     1.101% pgs not active
             316616/4737930 objects degraded (6.683%)
             433 active+clean
             53  active+undersized+degraded
             45  active+undersized+degraded+remapped+backfilling
             6   active+undersized+degraded+remapped+backfill_toofull
             4   undersized+degraded+remapped+backfilling+peered
             2   active+recovering+undersized+degraded+remapped
             2   undersized+degraded+remapped+backfill_toofull+peered
 
  io:
    client:   2.7 KiB/s rd, 704 MiB/s wr, 2 op/s rd, 1.90k op/s wr
    recovery: 117 MiB/s, 2 keys/s, 32 objects/s
```

# taking 3rd osd out - 13:45
- 13:55
```bash
sudo ceph -s
  cluster:
    id:     b5158006-fd1d-11ec-9283-279caa203eab
    health: HEALTH_WARN
            Failed to apply 2 service(s): osd.sff12-osd02-ssd-sep,osd.sff15-osd04-ssd-sep
            3 failed cephadm daemon(s)
            1 MDSs report slow metadata IOs
            15 backfillfull osd(s)
            2 nearfull osd(s)
            Reduced data availability: 13 pgs inactive
            Low space hindering backfill (add storage if this doesn't resolve itself): 80 pgs backfill_toofull
            Degraded data redundancy: 467610/4880586 objects degraded (9.581%), 162 pgs degraded, 135 pgs undersized
            3 pool(s) backfillfull
            2 daemons have recently crashed
 
  services:
    mon: 3 daemons, quorum sff13-mon02,sff17-mon03,lff11-mon01 (age 113m)
    mgr: lff11-mon01.wyprnu(active, since 22h), standbys: sff17-mon03.vfzejr, sff13-mon02.zmessl
    mds: 1/1 daemons up, 4 standby
    osd: 26 osds: 23 up (since 10m), 23 in (since 44s); 162 remapped pgs
 
  data:
    volumes: 1/1 healthy
    pools:   3 pools, 545 pgs
    objects: 1.63M objects, 6.0 TiB
    usage:   17 TiB used, 2.5 TiB / 20 TiB avail
    pgs:     2.385% pgs not active
             467610/4880586 objects degraded (9.581%)
             383 active+clean
             77  active+undersized+degraded+remapped+backfilling
             68  active+undersized+degraded+remapped+backfill_toofull
             10  undersized+degraded+remapped+backfill_toofull+peered
             3   undersized+degraded+remapped+backfilling+peered
             2   active+recovering+undersized+degraded+remapped
             2   active+undersized+degraded+remapped+backfill_wait+backfill_toofull
 
  io:
    client:   4.5 KiB/s rd, 686 MiB/s wr, 4 op/s rd, 1.20k op/s wr
    recovery: 171 MiB/s, 4 keys/s, 47 objects/s
```
# NO PROBLEM SO FAR

# turn off a osd host - 13:55 (2 hosts remainig)
- after taking out a host clients stopped
- 26 osds - 15 up - 11 down - 7 out - 9 nearfull


```bash
sudo ceph -s
  cluster:
    id:     b5158006-fd1d-11ec-9283-279caa203eab
    health: HEALTH_WARN
            Failed to apply 3 service(s): osd.sff12-osd02-ssd-sep,osd.sff14-osd03-ssd-sep,osd.sff15-osd04-ssd-sep
            3 failed cephadm daemon(s)
            1 hosts fail cephadm check
            1 MDSs report slow metadata IOs
            1 MDSs report slow requests
            1 backfillfull osd(s)
            8 osds down
            1 host (8 osds) down
            7 nearfull osd(s)
            Reduced data availability: 157 pgs inactive, 13 pgs down
            Low space hindering backfill (add storage if this doesn't resolve itself): 86 pgs backfill_toofull
            Degraded data redundancy: 1959711/4794429 objects degraded (40.875%), 532 pgs degraded, 532 pgs undersized
            3 pool(s) backfillfull
            2 daemons have recently crashed
 
  services:
    mon: 3 daemons, quorum sff13-mon02,sff17-mon03,lff11-mon01 (age 2h)
    mgr: lff11-mon01.wyprnu(active, since 22h), standbys: sff17-mon03.vfzejr, sff13-mon02.zmessl
    mds: 1/1 daemons up, 4 standby
    osd: 26 osds: 15 up (since 9m), 23 in (since 11m); 145 remapped pgs
 
  data:
    volumes: 1/1 healthy
    pools:   3 pools, 545 pgs
    objects: 1.60M objects, 5.9 TiB
    usage:   17 TiB used, 2.4 TiB / 20 TiB avail
    pgs:     28.807% pgs not active
             1959711/4794429 objects degraded (40.875%)
             386 active+undersized+degraded
             86  undersized+degraded+remapped+backfill_toofull+peered
             58  undersized+degraded+remapped+backfilling+peered
             13  down
             1   active+recovering+undersized+degraded+remapped
             1   active+recovering+undersized+degraded
 
  io:
    recovery: 162 MiB/s, 6 keys/s, 47 objects/s
```



## 14:17
```bash
sudo ceph -s
  cluster:
    id:     b5158006-fd1d-11ec-9283-279caa203eab
    health: HEALTH_WARN
            Failed to apply 3 service(s): osd.sff12-osd02-ssd-sep,osd.sff14-osd03-ssd-sep,osd.sff15-osd04-ssd-sep
            3 failed cephadm daemon(s)
            1 hosts fail cephadm check
            1 MDSs report slow metadata IOs
            1 MDSs report slow requests
            1 backfillfull osd(s)
            4 osds down
            1 host (8 osds) down
            8 nearfull osd(s)
            Reduced data availability: 154 pgs inactive, 13 pgs down
            Low space hindering backfill (add storage if this doesn't resolve itself): 86 pgs backfill_toofull
            Degraded data redundancy: 1932845/4794432 objects degraded (40.314%), 532 pgs degraded, 532 pgs undersized
            3 pool(s) backfillfull
            2 daemons have recently crashed
 
  services:
    mon: 3 daemons, quorum sff13-mon02,sff17-mon03,lff11-mon01 (age 2h)
    mgr: lff11-mon01.wyprnu(active, since 22h), standbys: sff17-mon03.vfzejr, sff13-mon02.zmessl
    mds: 1/1 daemons up, 4 standby
    osd: 26 osds: 15 up (since 19m), 19 in (since 9m); 141 remapped pgs
 
  data:
    volumes: 1/1 healthy
    pools:   3 pools, 545 pgs
    objects: 1.60M objects, 5.9 TiB
    usage:   14 TiB used, 2.0 TiB / 16 TiB avail
    pgs:     28.257% pgs not active
             1932845/4794432 objects degraded (40.314%)
             391 active+undersized+degraded
             86  undersized+degraded+remapped+backfill_toofull+peered
             55  undersized+degraded+remapped+backfilling+peered
             13  down
 
  io:
    recovery: 153 MiB/s, 2 keys/s, 41 objects/s
```

# 14:40
```bash
sudo ceph -s
  cluster:
    id:     b5158006-fd1d-11ec-9283-279caa203eab
    health: HEALTH_WARN
            Failed to apply 3 service(s): osd.sff12-osd02-ssd-sep,osd.sff14-osd03-ssd-sep,osd.sff15-osd04-ssd-sep
            3 failed cephadm daemon(s)
            1 hosts fail cephadm check
            1 MDSs report slow metadata IOs
            1 MDSs report slow requests
            1 backfillfull osd(s)
            4 osds down
            1 host (8 osds) down
            11 nearfull osd(s)
            Reduced data availability: 135 pgs inactive, 13 pgs down
            Low space hindering backfill (add storage if this doesn't resolve itself): 86 pgs backfill_toofull
            Degraded data redundancy: 1892085/4794456 objects degraded (39.464%), 532 pgs degraded, 532 pgs undersized
            3 pool(s) backfillfull
            2 daemons have recently crashed
 
  services:
    mon: 3 daemons, quorum sff13-mon02,sff17-mon03,lff11-mon01 (age 2h)
    mgr: lff11-mon01.wyprnu(active, since 22h), standbys: sff17-mon03.vfzejr, sff13-mon02.zmessl
    mds: 1/1 daemons up, 4 standby
    osd: 26 osds: 15 up (since 41m), 19 in (since 31m); 122 remapped pgs
 
  data:
    volumes: 1/1 healthy
    pools:   3 pools, 545 pgs
    objects: 1.60M objects, 5.9 TiB
    usage:   14 TiB used, 1.9 TiB / 16 TiB avail
    pgs:     24.771% pgs not active
             1892085/4794456 objects degraded (39.464%)
             410 active+undersized+degraded
             86  undersized+degraded+remapped+backfill_toofull+peered
             36  undersized+degraded+remapped+backfilling+peered
             13  down
 
  io:
    recovery: 73 MiB/s, 0 keys/s, 19 objects/s
```
# 14:40 turn off a monitor
- 14:50
```bash
sudo ceph -s
  cluster:
    id:     b5158006-fd1d-11ec-9283-279caa203eab
    health: HEALTH_WARN
            Failed to apply 3 service(s): osd.sff12-osd02-ssd-sep,osd.sff14-osd03-ssd-sep,osd.sff15-osd04-ssd-sep
            3 failed cephadm daemon(s)
            2 hosts fail cephadm check
            1 filesystem is degraded
            1/3 mons down, quorum sff13-mon02,lff11-mon01
            1 backfillfull osd(s)
            4 osds down
            1 host (8 osds) down
            11 nearfull osd(s)
            Reduced data availability: 132 pgs inactive, 13 pgs down
            Low space hindering backfill (add storage if this doesn't resolve itself): 86 pgs backfill_toofull
            Degraded data redundancy: 1879685/4794456 objects degraded (39.205%), 532 pgs degraded, 531 pgs undersized
            3 pool(s) backfillfull
            2 daemons have recently crashed
 
  services:
    mon: 3 daemons, quorum sff13-mon02,lff11-mon01 (age 9m), out of quorum: sff17-mon03
    mgr: lff11-mon01.wyprnu(active, since 23h), standbys: sff13-mon02.zmessl
    mds: 1/1 daemons up, 2 standby
    osd: 26 osds: 15 up (since 52m), 19 in (since 42m); 119 remapped pgs
 
  data:
    volumes: 0/1 healthy, 1 recovering
    pools:   3 pools, 545 pgs
    objects: 1.60M objects, 5.9 TiB
    usage:   14 TiB used, 1.8 TiB / 16 TiB avail
    pgs:     24.220% pgs not active
             1879685/4794456 objects degraded (39.205%)
             413 active+undersized+degraded
             86  undersized+degraded+remapped+backfill_toofull+peered
             33  undersized+degraded+remapped+backfilling+peered
             13  down
 
  io:
    recovery: 67 MiB/s, 0 keys/s, 17 objects/s
```

# 16:00
```bash
  cluster:
    id:     b5158006-fd1d-11ec-9283-279caa203eab
    health: HEALTH_WARN
            Failed to apply 3 service(s): osd.sff12-osd02-ssd-sep,osd.sff14-osd03-ssd-sep,osd.sff15-osd04-ssd-sep
            3 failed cephadm daemon(s)
            2 hosts fail cephadm check
            1 filesystem is degraded
            1/3 mons down, quorum sff13-mon02,lff11-mon01
            1 backfillfull osd(s)
            4 osds down
            1 host (8 osds) down
            12 nearfull osd(s)
            Reduced data availability: 111 pgs inactive, 13 pgs down
            Low space hindering backfill (add storage if this doesn't resolve itself): 86 pgs backfill_toofull
            Degraded data redundancy: 1848911/4794456 objects degraded (38.564%), 532 pgs degraded, 532 pgs undersized
            3 pool(s) backfillfull
            2 daemons have recently crashed
 
  services:
    mon: 3 daemons, quorum sff13-mon02,lff11-mon01 (age 78m), out of quorum: sff17-mon03
    mgr: lff11-mon01.wyprnu(active, since 24h), standbys: sff13-mon02.zmessl
    mds: 1/1 daemons up, 2 standby
    osd: 26 osds: 15 up (since 2h), 19 in (since 112m); 98 remapped pgs
 
  data:
    volumes: 0/1 healthy, 1 recovering
    pools:   3 pools, 545 pgs
    objects: 1.60M objects, 5.9 TiB
    usage:   14 TiB used, 1.7 TiB / 16 TiB avail
    pgs:     20.367% pgs not active
             1848911/4794456 objects degraded (38.564%)
             434 active+undersized+degraded
             86  undersized+degraded+remapped+backfill_toofull+peered
             13  down
             12  undersized+degraded+remapped+backfilling+peered
 
  io:
    recovery: 17 MiB/s, 4 objects/s
```