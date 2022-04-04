# what we should do
- configue by [getting started](./getting-started.md)
- benchmark every step and compare resaults

## Hardware
1. use SSD for WAL
2. 10Gb network at least
3. use fastest CPU we have
4. az usual more RAM is better

## Software
1. cpu sleep step
2. RAM to use total RAM availble
3. Scrubbing
4. OP (operation) priorities
5. Network
6. General system tuning
7. Tuning CephFS
8. PG distributions


# sample architecture
## OSD
- RAM 64 GB
- CPU Intel(R) Xeon(R) CPU E5-2690 v2 @ 3.00GHz
- disks 12 HDD - 1 spair HDD - 1 SSD (WAL)
### configuration
- RAM per OSD 5GB
- CPU per OSD 1 core


> # STEP 1:
## what we do!
- inserting 4K's from 3 servers and mesuring IOPS
- configure CPU sleep state on all hosts
- [See](https://askubuntu.com/questions/749349/how-to-set-intel-idle-max-cstate-1)

## Befor
![iops01](./images/iops01)
![latency01](./images/latency01)

## After
![iops02](./images/iops02)
![latency02](./images/latency02)

## Resaults
![resault01](./images/resault01)
![resault01](./images/resault02)
