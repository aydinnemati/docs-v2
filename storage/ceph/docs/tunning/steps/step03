# STEP 3:
## what we will do!?
- configure network & general system tunning
- mastering ceph page 237 - NETWORK
- add below configuration to /etc/sysctl.conf for network
```bash
#Network buffers
net.core.rmem_max = 56623104
net.core.wmem_max = 56623104
net.core.rmem_default = 56623104
net.core.wmem_default = 56623104
net.core.optmem_max = 40960
net.ipv4.tcp_rmem = 4096 87380 56623104
net.ipv4.tcp_wmem = 4096 65536 56623104
#Maximum connections and backlog
net.core.somaxconn = 1024
net.core.netdev_max_backlog = 50000
#TCP tuning options
net.ipv4.tcp_max_syn_backlog = 30000
net.ipv4.tcp_max_tw_buckets = 2000000
net.ipv4.tcp_tw_reuse = 1
net.ipv4.tcp_tw_recycle = 1
net.ipv4.tcp_fin_timeout = 10
#Don't use slow start on idle TCP connections
net.ipv4.tcp_slow_start_after_idle = 0
```
- add below configuration to /etc/sysctl.conf for general system tunning
```bash
# Make sure that the system has sufficient memory free at all times:
vm/min_free_kbytes = 524288
# Increase the maximum number of allowed processes:
kernel.pid_max=4194303
# Use the following to set the maximum number of file handles:
fs.file-max=26234859
```