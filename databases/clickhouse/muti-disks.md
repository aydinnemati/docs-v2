# add disks to default volume of clickhouse

- for adding new disk to default clickhouse volume, should create a `default` named policy like below with new disk:

```xml
     <storage_configuration>
         <disks>
             <default>
             </default>
             <storage01>
                 <path>/mnt/storage01/</path>
             </storage01>
         </disks>
 
         <policies>
             <prefer_new_disk>
                 <volumes>
                     <default>
                         <disk>default</disk>
                         <disk>storage01</disk>
                         <load_balancing>least_used</load_balancing>
                     </default>
                 </volumes>
             </prefer_new_disk>
         </policies>
     </storage_configuration>
```