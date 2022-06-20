# finding disks related to osds
See [ubuntu.com](https://ubuntu.com/ceph/docs/replacing-osd-disks)

```bash
$ sudo pvs
```
```bash
$ sudo lsblk -i -o NAME,FSTYPE
```


# finding osd disk name on os
1. osd config path (cat /var/lib/ceph/751fdb18-e648-11ec-b5ab-110e9bfd061c/osd.{{OSD.ID}}/fsid)
- get osd fsid, should be like
```bash
f4723652-c643-4622-802e-7b4713c2819e
```
2. then keep first part number and find disk by command below
```bash
$ sudo lsblk  | grep { first part of fsid} -B 1
```
3. also can use this to find osd disk, wal and db
```bash
$ sudo lvs
  LV                                             VG                                            Attr       LSize    Pool Origin Data%  Meta%  Move Log Cpy%Sync Convert
  osd-block-d884106d-8875-4796-8568-8e07a4372054 ceph-0c79fdc2-2a74-4e3e-b90c-6e6810715693     -wi-ao---- <838.36g                                                    
  osd-block-5bae0797-1ae0-436a-8b88-d3e51422653b ceph-13311b6f-80e5-4e84-8b75-1341fc05a769     -wi-ao---- <838.36g                                                    
  osd-block-be970d82-0662-473a-8a40-555d7f393c7e ceph-3f1779c0-4800-46f8-994b-355a10de7800     -wi-ao---- <838.36g                                                    
  osd-block-a5b8d29c-6d58-469e-a01e-367839d4ef2e ceph-477d66ee-edc7-49c2-b053-6617a472849b     -wi-ao---- <838.36g                                                    
  osd-block-f4723652-c643-4622-802e-7b4713c2819e ceph-957daf7a-79ce-4009-b08d-75d99f654cb2     -wi-a----- <838.36g                                                    
  osd-block-2dfde134-e02e-4ce2-928f-531667b23def ceph-96e27a9f-886e-45ef-9a60-7e2cd2adc751     -wi-ao---- <838.36g                                                    
  osd-block-e38c7c7f-c790-494c-b16f-9afe3f4b17b7 ceph-b4e13c24-385f-4599-9cf1-3033da515df0     -wi-ao---- <838.36g                                                    
  osd-block-d150b89c-f820-4965-b6f2-be581b129f95 ceph-f2d6dc6b-8cce-4356-affd-d3875306b04d     -wi-ao---- <838.36g                                                    
  ceph-ir-aasaam-r1-storage01-ceph-osd-03-db00   ceph-ir-aasaam-r1-storage01-ceph-osd-03-ssd00 -wi-ao----   35.00g                                                    
  ceph-ir-aasaam-r1-storage01-ceph-osd-03-db01   ceph-ir-aasaam-r1-storage01-ceph-osd-03-ssd00 -wi-ao----   35.00g                                                    
  ceph-ir-aasaam-r1-storage01-ceph-osd-03-db02   ceph-ir-aasaam-r1-storage01-ceph-osd-03-ssd00 -wi-ao----   35.00g                                                    
  ceph-ir-aasaam-r1-storage01-ceph-osd-03-db03   ceph-ir-aasaam-r1-storage01-ceph-osd-03-ssd00 -wi-ao----   35.00g                                                    
  ceph-ir-aasaam-r1-storage01-ceph-osd-03-db04   ceph-ir-aasaam-r1-storage01-ceph-osd-03-ssd00 -wi-a-----   35.00g                                                    
  ceph-ir-aasaam-r1-storage01-ceph-osd-03-db05   ceph-ir-aasaam-r1-storage01-ceph-osd-03-ssd00 -wi-ao----   35.00g                                                    
  ceph-ir-aasaam-r1-storage01-ceph-osd-03-db06   ceph-ir-aasaam-r1-storage01-ceph-osd-03-ssd00 -wi-ao----   35.00g                                                    
  ceph-ir-aasaam-r1-storage01-ceph-osd-03-db07   ceph-ir-aasaam-r1-storage01-ceph-osd-03-ssd00 -wi-ao----   35.00g                                                    
  ceph-ir-aasaam-r1-storage01-ceph-osd-03-db08   ceph-ir-aasaam-r1-storage01-ceph-osd-03-ssd00 -wi-a-----   35.00g                                                    
  ceph-ir-aasaam-r1-storage01-ceph-osd-03-wal00  ceph-ir-aasaam-r1-storage01-ceph-osd-03-ssd00 -wi-ao----   45.00g                                                    
  ceph-ir-aasaam-r1-storage01-ceph-osd-03-wal01  ceph-ir-aasaam-r1-storage01-ceph-osd-03-ssd00 -wi-ao----   45.00g                                                    
  ceph-ir-aasaam-r1-storage01-ceph-osd-03-wal02  ceph-ir-aasaam-r1-storage01-ceph-osd-03-ssd00 -wi-ao----   45.00g                                                    
  ceph-ir-aasaam-r1-storage01-ceph-osd-03-wal03  ceph-ir-aasaam-r1-storage01-ceph-osd-03-ssd00 -wi-ao----   45.00g                                                    
  ceph-ir-aasaam-r1-storage01-ceph-osd-03-wal04  ceph-ir-aasaam-r1-storage01-ceph-osd-03-ssd00 -wi-a-----   45.00g                                                    
  ceph-ir-aasaam-r1-storage01-ceph-osd-03-wal05  ceph-ir-aasaam-r1-storage01-ceph-osd-03-ssd00 -wi-ao----   45.00g                                                    
  ceph-ir-aasaam-r1-storage01-ceph-osd-03-wal06  ceph-ir-aasaam-r1-storage01-ceph-osd-03-ssd00 -wi-ao----   45.00g                                                    
  ceph-ir-aasaam-r1-storage01-ceph-osd-03-wal07  ceph-ir-aasaam-r1-storage01-ceph-osd-03-ssd00 -wi-ao----   45.00g                                                    
  ceph-ir-aasaam-r1-storage01-ceph-osd-03-wal08  ceph-ir-aasaam-r1-storage01-ceph-osd-03-ssd00 -wi-a-----   45.00g 
```
- Attr (a) means active and (o) means open, when osd is down lv is not opend like example ahead.