# finding lvm (wal/db) block device path
> you can read metedata (path of wal/db too) of an OSD in panel or command below:
- in panel go to cluster > OSDs > click on one of them to see tabs and metedata tab
- in command line run command below
   ```bash
   $ ceph osd metadata osd.*>ID<*
   ```
> then when you find wal/db path can find exact lvm with this command
```bash
$ lvdisplay | awk  '/LV Name/{n=$3} /Block device/{d=$3; sub(".*:","dm-",d); print d,n;}'
```

__* TIP: you should know that in `lvdisplay` command in section `Block Device` its a number like 253 and base on linux kernel it means dm- and folloing with a `:N` and it means like number after `dm-`, after all when you see this `253:6` is same as `dm-6`*__