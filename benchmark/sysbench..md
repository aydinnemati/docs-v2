#/usr/local/sysbench_1/bin/sysbench fileio help
sysbench 1.0.9 (using bundled LuaJIT 2.1.0-beta2)

fileio options:
  --file-num=N              number of files to create [128]
  --file-block-size=N       block size to use in all IO operations [16384]
  --file-total-size=SIZE    total size of files to create [2G]
  --file-test-mode=STRING   test mode {seqwr, seqrewr, seqrd, rndrd, rndwr, rndrw}
  --file-io-mode=STRING     file operations mode {sync,async,mmap} [sync]
  --file-async-backlog=N    number of asynchronous operatons to queue per thread [128]
  --file-extra-flags=STRING additional flags to use on opening files {sync,dsync,direct} []
  --file-fsync-freq=N       do fsync() after this number of requests (0 - don't use fsync()) [100]
  --file-fsync-all[=on|off] do fsync() after each write operation [off]
  --file-fsync-end[=on|off] do fsync() at the end of test [on]
  --file-fsync-mode=STRING  which method to use for synchronization {fsync, fdatasync} [fsync]
  --file-merged-requests=N  merge at most this number of IO requests if possible (0 - don't merge) [0]
  --file-rw-ratio=N         reads/writes ratio for combined test [1.5]