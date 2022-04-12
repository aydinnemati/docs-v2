# Test 4 - SSD - WAL - DB
- taking out WAL/DB disk and see what happens

# Befor
## status
### CMD
```bash
$ sudo ceph status
```
```text
  cluster:
    id:     fb2f1a10-b97b-11ec-a1cf-d31a644d07f3
    health: HEALTH_OK
 
  services:
    mon: 4 daemons, quorum lff-11,sff-13,sff-18,sff-17 (age 2h)
    mgr: sff-13.xmridy(active, since 2h), standbys: lff-11.majfec, sff-18.wbancv, sff-17.dumagb
    mds: 1/1 daemons up, 4 standby
    osd: 45 osds: 45 up (since 2h), 45 in (since 22h)
 
  data:
    volumes: 1/1 healthy
    pools:   3 pools, 65 pgs
    objects: 12.73M objects, 28 GiB
    usage:   1.6 TiB used, 37 TiB / 38 TiB avail
    pgs:     65 active+clean
```
### CMD
```bash
$ sudo ceph osd df tree
```
```text
ID   CLASS  WEIGHT    REWEIGHT  SIZE     RAW USE  DATA     OMAP     META      AVAIL    %USE  VAR   PGS  STATUS  TYPE NAME      
 -1         38.38005         -   38 TiB  1.6 TiB   86 GiB   24 GiB    46 GiB   37 TiB  4.23  1.00    -          root default   
 -3          7.67601         -  7.7 TiB  329 GiB   14 GiB  4.7 GiB   8.9 GiB  7.4 TiB  4.19  0.99    -              host sff-10
  0    hdd   0.85289   1.00000  873 GiB   36 GiB  932 MiB  306 MiB   834 MiB  837 GiB  4.11  0.97    2      up          osd.0  
  1    hdd   0.85289   1.00000  873 GiB   37 GiB  1.8 GiB  462 MiB   1.2 GiB  837 GiB  4.21  1.00    4      up          osd.1  
  2    hdd   0.85289   1.00000  873 GiB   35 GiB   15 MiB  309 MiB   295 MiB  838 GiB  4.01  0.95    1      up          osd.2  
  3    hdd   0.85289   1.00000  873 GiB   37 GiB  1.8 GiB  828 MiB   1.2 GiB  837 GiB  4.21  1.00    5      up          osd.3  
  4    hdd   0.85289   1.00000  873 GiB   37 GiB  1.8 GiB  735 MiB   996 MiB  837 GiB  4.21  1.00    5      up          osd.4  
  5    hdd   0.85289   1.00000  873 GiB   37 GiB  1.8 GiB  708 MiB   990 MiB  837 GiB  4.21  1.00    5      up          osd.5  
  6    hdd   0.85289   1.00000  873 GiB   36 GiB  937 MiB  734 MiB   1.3 GiB  837 GiB  4.11  0.97    4      up          osd.6  
  7    hdd   0.85289   1.00000  873 GiB   36 GiB  909 MiB      0 B   321 MiB  837 GiB  4.11  0.97    1      up          osd.7  
  8    hdd   0.85289   1.00000  873 GiB   39 GiB  4.4 GiB  702 MiB   1.7 GiB  834 GiB  4.52  1.07    8      up          osd.8  
 -5          7.67601         -  7.7 TiB  331 GiB   16 GiB  4.5 GiB   7.9 GiB  7.4 TiB  4.21  1.00    -              host sff-12
  9    hdd   0.85289   1.00000  873 GiB   38 GiB  2.7 GiB  489 MiB   1.1 GiB  836 GiB  4.31  1.02    5      up          osd.9  
 10    hdd   0.85289   1.00000  873 GiB   36 GiB  912 MiB      0 B   321 MiB  837 GiB  4.11  0.97    2      up          osd.10 
 11    hdd   0.85289   1.00000  873 GiB   38 GiB  2.7 GiB  785 MiB   1.1 GiB  836 GiB  4.31  1.02    6      up          osd.11 
 12    hdd   0.85289   1.00000  873 GiB   35 GiB   38 MiB  1.3 GiB   874 MiB  838 GiB  4.01  0.95    5      up          osd.12 
 13    hdd   0.85289   1.00000  873 GiB   38 GiB  2.7 GiB  556 MiB   816 MiB  836 GiB  4.31  1.02    5      up          osd.13 
 14    hdd   0.85289   1.00000  873 GiB   38 GiB  2.6 GiB  227 MiB   1.2 GiB  836 GiB  4.31  1.02    4      up          osd.14 
 15    hdd   0.85289   1.00000  873 GiB   37 GiB  1.8 GiB  725 MiB   978 MiB  837 GiB  4.21  1.00    5      up          osd.15 
 16    hdd   0.85289   1.00000  873 GiB   36 GiB  917 MiB  244 MiB   708 MiB  837 GiB  4.11  0.97    2      up          osd.16 
 17    hdd   0.85289   1.00000  873 GiB   37 GiB  1.8 GiB  271 MiB   965 MiB  837 GiB  4.21  1.00    3      up          osd.17 
-11          7.67601         -  7.7 TiB  332 GiB   17 GiB  4.7 GiB   9.3 GiB  7.4 TiB  4.22  1.00    -              host sff-14
 36    hdd   0.85289   1.00000  873 GiB   35 GiB   12 MiB  294 MiB   338 MiB  838 GiB  4.01  0.95    1      up          osd.36 
 37    hdd   0.85289   1.00000  873 GiB   38 GiB  2.7 GiB  793 MiB   1.0 GiB  836 GiB  4.31  1.02    6      up          osd.37 
 38    hdd   0.85289   1.00000  873 GiB   36 GiB  934 MiB  586 MiB   829 MiB  837 GiB  4.11  0.97    3      up          osd.38 
 39    hdd   0.85289   1.00000  873 GiB   38 GiB  2.7 GiB  496 MiB   1.0 GiB  836 GiB  4.31  1.02    5      up          osd.39 
 40    hdd   0.85289   1.00000  873 GiB   37 GiB  1.8 GiB  443 MiB   1.5 GiB  837 GiB  4.21  1.00    4      up          osd.40 
 41    hdd   0.85289   1.00000  873 GiB   39 GiB  3.5 GiB  488 MiB   1.1 GiB  835 GiB  4.41  1.04    6      up          osd.41 
 42    hdd   0.85289   1.00000  873 GiB   36 GiB  914 MiB  459 MiB   1.1 GiB  837 GiB  4.11  0.97    3      up          osd.42 
 43    hdd   0.85289   1.00000  873 GiB   38 GiB  2.6 GiB      0 B   935 MiB  836 GiB  4.31  1.02    3      up          osd.43 
 44    hdd   0.85289   1.00000  873 GiB   37 GiB  1.8 GiB  1.2 GiB   1.5 GiB  837 GiB  4.21  1.00    7      up          osd.44 
 -9          7.67601         -  7.7 TiB  338 GiB   23 GiB  4.0 GiB   8.3 GiB  7.3 TiB  4.30  1.02    -              host sff-15
 27    hdd   0.85289   1.00000  873 GiB   37 GiB  1.8 GiB  745 MiB   972 MiB  837 GiB  4.21  1.00    5      up          osd.27 
 28    hdd   0.85289   1.00000  873 GiB   35 GiB   51 MiB  514 MiB   708 MiB  838 GiB  4.01  0.95    2      up          osd.28 
 29    hdd   0.85289   1.00000  873 GiB   37 GiB  1.8 GiB  318 MiB   949 MiB  837 GiB  4.21  1.00    3      up          osd.29 
 30    hdd   0.85289   1.00000  873 GiB   39 GiB  3.5 GiB  510 MiB   1.0 GiB  835 GiB  4.41  1.04    6      up          osd.30 
 31    hdd   0.85289   1.00000  873 GiB   35 GiB   11 MiB      0 B    23 MiB  838 GiB  4.01  0.95    0      up          osd.31 
 32    hdd   0.85289   1.00000  873 GiB   39 GiB  4.4 GiB  249 MiB  1006 MiB  834 GiB  4.51  1.07    6      up          osd.32 
 33    hdd   0.85289   1.00000  873 GiB   40 GiB  5.3 GiB  547 MiB   1.2 GiB  833 GiB  4.61  1.09    8      up          osd.33 
 34    hdd   0.85289   1.00000  873 GiB   39 GiB  3.5 GiB  462 MiB   1.1 GiB  835 GiB  4.41  1.04    7      up          osd.34 
 35    hdd   0.85289   1.00000  873 GiB   38 GiB  2.7 GiB  754 MiB   1.4 GiB  836 GiB  4.31  1.02    6      up          osd.35 
 -7          7.67601         -  7.7 TiB  330 GiB   15 GiB  5.8 GiB    11 GiB  7.4 TiB  4.20  0.99    -              host sff-16
 18    hdd   0.85289   1.00000  873 GiB   36 GiB  931 MiB  743 MiB   1.4 GiB  837 GiB  4.11  0.97    4      up          osd.18 
 19    hdd   0.85289   1.00000  873 GiB   36 GiB  941 MiB  499 MiB   894 MiB  837 GiB  4.11  0.97    3      up          osd.19 
 20    hdd   0.85289   1.00000  873 GiB   37 GiB  1.8 GiB  501 MiB   1.5 GiB  837 GiB  4.21  1.00    5      up          osd.20 
 21    hdd   0.85289   1.00000  873 GiB   39 GiB  3.5 GiB  494 MiB   1.2 GiB  835 GiB  4.41  1.04    6      up          osd.21 
 22    hdd   0.85289   1.00000  873 GiB   36 GiB  922 MiB  836 MiB   1.3 GiB  837 GiB  4.11  0.97    4      up          osd.22 
 23    hdd   0.85289   1.00000  873 GiB   39 GiB  3.5 GiB  221 MiB   1.6 GiB  835 GiB  4.41  1.04    5      up          osd.23 
 24    hdd   0.85289   1.00000  873 GiB   35 GiB   49 MiB  1.6 GiB   1.7 GiB  838 GiB  4.01  0.95    7      up          osd.24 
 25    hdd   0.85289   1.00000  873 GiB   38 GiB  2.7 GiB  241 MiB   1.2 GiB  836 GiB  4.31  1.02    4      up          osd.25 
 26    hdd   0.85289   1.00000  873 GiB   36 GiB  943 MiB  778 MiB   694 MiB  837 GiB  4.11  0.97    4      up          osd.26 
                         TOTAL   38 TiB  1.6 TiB   86 GiB   24 GiB    46 GiB   37 TiB  4.23                                    
MIN/MAX VAR: 0.95/1.09  STDDEV: 0.15
```
### CMD
```bash
$ sudo ceph orch ls
```
```text
NAME                             PORTS        RUNNING  REFRESHED  AGE  PLACEMENT                            
alertmanager                     ?:9093,9094      1/1  4m ago     1h   lff-11;count:1                       
crash                                             9/9  6m ago     1h   *                                    
grafana                          ?:3000           1/1  4m ago     0h   lff-11;count:1                       
mds.test-fs                                       5/5  6m ago     22h  lff-11;sff-13;sff-18;sff-17;count:5  
mgr                                               4/5  6m ago     0h   lff-11;sff-13;sff-18;sff-17;count:5  
mon                                               4/5  6m ago     0h   lff-11;sff-13;sff-18;sff-17;count:5  
node-exporter                    ?:9100           9/9  6m ago     1h   *                                    
osd.osd_wal_db_seperated_sff-10                     9  6m ago     5h   sff-10                               
osd.osd_wal_db_seperated_sff-12                     9  4m ago     5h   sff-12                               
osd.osd_wal_db_seperated_sff-14                     9  4m ago     4h   sff-14                               
osd.osd_wal_db_seperated_sff-15                     9  4m ago     4h   sff-15                               
osd.osd_wal_db_seperated_sff-16                     9  4m ago     4h   sff-16                               
prometheus                       ?:9095           1/1  4m ago     0h   lff-11;count:1                       
```
# After
1. node OSD's are DOWN after taking out SSD disk (WAL/DB)
```bash
  cluster:
    id:     fb2f1a10-b97b-11ec-a1cf-d31a644d07f3
    health: HEALTH_WARN
            9 osds down
            1 host (9 osds) down
            Degraded data redundancy: 6868860/38195115 objects degraded (17.984%), 35 pgs degraded, 35 pgs undersized
 
  services:
    mon: 4 daemons, quorum lff-11,sff-13,sff-18,sff-17 (age 2h)
    mgr: sff-13.xmridy(active, since 2h), standbys: lff-11.majfec, sff-18.wbancv, sff-17.dumagb
    mds: 1/1 daemons up, 4 standby
    osd: 45 osds: 36 up (since 94s), 45 in (since 22h)
 
  data:
    volumes: 1/1 healthy
    pools:   3 pools, 65 pgs
    objects: 12.73M objects, 28 GiB
    usage:   1.6 TiB used, 37 TiB / 38 TiB avail
    pgs:     6868860/38195115 objects degraded (17.984%)
             35 active+undersized+degraded
             30 active+clean
```
```bash
[WRN] OSD_DOWN: 9 osds down
    osd.0 (root=default,host=sff-10) is down
    osd.1 (root=default,host=sff-10) is down
    osd.2 (root=default,host=sff-10) is down
    osd.3 (root=default,host=sff-10) is down
    osd.4 (root=default,host=sff-10) is down
    osd.5 (root=default,host=sff-10) is down
    osd.6 (root=default,host=sff-10) is down
    osd.7 (root=default,host=sff-10) is down
    osd.8 (root=default,host=sff-10) is down
[WRN] OSD_HOST_DOWN: 1 host (9 osds) down
    host sff-10 (root=default) (9 osds) is down
[WRN] PG_DEGRADED: Degraded data redundancy: 6868860/38195115 objects degraded (17.984%), 35 pgs degraded, 35 pgs undersized
    pg 2.0 is stuck undersized for 2m, current state active+undersized+degraded, last acting [17,24]
    pg 2.1 is stuck undersized for 2m, current state active+undersized+degraded, last acting [27,26]
    pg 2.2 is stuck undersized for 2m, current state active+undersized+degraded, last acting [41,15]
    pg 2.4 is stuck undersized for 2m, current state active+undersized+degraded, last acting [18,42]
```
2. putting same disk in
3. after afew minutes OSD's that were UP - DOWN changed to OUT - DOWN and cluster started recovery.
4. rebooting node
5. OSD's are up and running after server boots up :) (putting back SSD same **BAY** it was)
6. **HEALTH_OK** after redeploy OSD's
```text
  cluster:
    id:     fb2f1a10-b97b-11ec-a1cf-d31a644d07f3
    health: HEALTH_OK
 
  services:
    mon: 4 daemons, quorum lff-11,sff-13,sff-18,sff-17 (age 3h)
    mgr: sff-13.xmridy(active, since 3h), standbys: lff-11.majfec, sff-18.wbancv, sff-17.dumagb
    mds: 1/1 daemons up, 4 standby
    osd: 45 osds: 45 up (since 5m), 45 in (since 5m)
 
  data:
    volumes: 1/1 healthy
    pools:   3 pools, 65 pgs
    objects: 12.73M objects, 28 GiB
    usage:   1.6 TiB used, 37 TiB / 38 TiB avail
    pgs:     65 active+clean
```