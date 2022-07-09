# Miscellaneous
See [ceph docs](https://docs.ceph.com/en/quincy/rados/operations/health-checks/)
## RECENT_CRASH
- One or more Ceph daemons has crashed recently, and the crash has not yet been archived (acknowledged) by the administrator. This may indicate a software bug, a hardware problem (e.g., a failing disk), or some other problem.
New crashes can be listed with:
```bash
$ sudo ceph crash ls-new
```
- Information about a specific crash can be examined with:
```bash
$ ceph crash info <crash-id>
```
- This warning can be silenced by “archiving” the crash (perhaps after being examined by an administrator) so that it does not generate this warning:
```bash
$ sudo ceph crash archive <crash-id>
```
> ### Archived crashes will still be visible via _**ceph crash ls**_ but not _**ceph crash ls-new**_