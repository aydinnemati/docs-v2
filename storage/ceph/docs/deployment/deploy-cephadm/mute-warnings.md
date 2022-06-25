# ceph warnings - mute

- POOL_NO_REDUNDANCY
```bash
$ sudo ceph health mute POOL_NO_REDUNDANCY
$ sudo ceph -s
cluster:
    id:     9d6d920c-f162-11ec-8ec7-85a0e3613844
    health: HEALTH_OK
            (muted: POOL_NO_REDUNDANCY)
```