```bash
#!/bin/sh
x=10000
COUNT=1
BASE=4096
echo "enter bs: "
read BASE
echo "enter count: "
read COUNT

while [ $x -lt 1000000000000 ]
do
  #mkdir -p  /data-ceph/DD05/$x/$x/$x

#  dd if=/dev/zero of=/data-ceph/DD05/$x/$x/$x/file-$x bs=$BASE count=$COUNT
  echo "bs="$BASE "count="$COUNT "file="$x
  x=$((x+1))
  sleep 0.01
done

```