# OSD Recovery Priority
1. osd_recovery_max_active
```bash
$ sudo ceph config set osd  osd_recovery_max_active
$ sudo ceph config set osd  osd_recovery_max_active *<NUMBER>*
```
2. osd_recovery_sleep
```bash
$ sudo ceph config get osd  osd_recovery_sleep
$ sudo ceph config set osd osd_recovery_sleep *<NUMBER>*
```
3. osd_max_backfills
```bash
$ sudo ceph config get osd  osd_max_backfills
$ sudo ceph config set osd osd_max_backfills *<NUMBER>*
```
4. osd_recovery_max_single_start
```bash
$ sudo ceph config get osd  osd_recovery_max_single_start
$ sudo ceph config set osd osd_recovery_max_single_start *<NUMBER>*
```