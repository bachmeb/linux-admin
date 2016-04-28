# meminfo

## References
* http://www.cyberciti.biz/faq/linux-system-memory-utilization/
* https://www.centos.org/docs/5/html/5.1/Deployment_Guide/s2-proc-meminfo.html
* https://github.com/torvalds/linux/blob/master/Documentation/filesystems/proc.txt

```
cat /proc/meminfo
```
```c
/*
MemTotal:      8033836 kB
MemFree:       1846968 kB
Buffers:        220408 kB
Cached:        4704716 kB
SwapCached:          0 kB
Active:        3381120 kB
Inactive:      2573284 kB
HighTotal:           0 kB
HighFree:            0 kB
LowTotal:      8033836 kB
LowFree:       1846968 kB
SwapTotal:     7815580 kB
SwapFree:      7815444 kB
Dirty:              44 kB
Writeback:           0 kB
AnonPages:     1029232 kB
Mapped:          25092 kB
Slab:           195628 kB
PageTables:       8476 kB
NFS_Unstable:        0 kB
Bounce:              0 kB
CommitLimit:  11832496 kB
Committed_AS:  1449200 kB
VmallocTotal: 34359738367 kB
VmallocUsed:    268816 kB
VmallocChunk: 34359468923 kB
*/
```


* MemTotal
  * Total amount of physical RAM, in kilobytes.
* MemFree
  * The amount of physical RAM, in kilobytes, left unused by the system.
* Buffers
  * The amount of physical RAM, in kilobytes, used for file buffers.
* Cached
  * The amount of physical RAM, in kilobytes, used as cache memory.
* SwapCached
  * The amount of swap, in kilobytes, used as cache memory.
* Active
  * The total amount of buffer or page cache memory, in kilobytes, that is in active use. This is memory that has been recently used and is usually not reclaimed for other purposes.
* Inactive
  * The total amount of buffer or page cache memory, in kilobytes, that are free and available. This is memory that has not been recently used and can be reclaimed for other purposes.
* HighTotal and HighFree
  * The total and free amount of memory, in kilobytes, that is not directly mapped into kernel space. The HighTotal value can vary based on the type of kernel used.
* LowTotal and LowFree
  * The total and free amount of memory, in kilobytes, that is directly mapped into kernel space. The LowTotal value can vary based on the type of kernel used.
* SwapTotal
  * The total amount of swap available, in kilobytes.
* SwapFree
  * The total amount of swap free, in kilobytes.
* Dirty
  * The total amount of memory, in kilobytes, waiting to be written back to the disk.
* Writeback
  * The total amount of memory, in kilobytes, actively being written back to the disk.
* Mapped
  * The total amount of memory, in kilobytes, which have been used to map devices, files, or libraries using the mmap command.
* Slab
  * The total amount of memory, in kilobytes, used by the kernel to cache data structures for its own use.
* Committed_AS
  * The total amount of memory, in kilobytes, estimated to complete the workload. This value represents the worst case scenario value, and also includes swap memory.
* PageTables
  * The total amount of memory, in kilobytes, dedicated to the lowest page table level.
* VMallocTotal
  * The total amount of memory, in kilobytes, of total allocated virtual address space.
* VMallocUsed
  * The total amount of memory, in kilobytes, of used virtual address space.
* VMallocChunk
  * The largest contiguous block of memory, in kilobytes, of available virtual address space.
* HugePages_Total
  * The total number of hugepages for the system. The number is derived by dividing Hugepagesize by the megabytes set aside for hugepages specified in /proc/sys/vm/hugetlb_pool. This statistic only appears on the x86, Itanium, and AMD64 architectures.
* HugePages_Free
  * The total number of hugepages available for the system. This statistic only appears on the x86, Itanium, and AMD64 architectures.
* Hugepagesize
  * The size for each hugepages unit in kilobytes. By default, the value is 4096 KB on uniprocessor kernels for 32 bit architectures. For SMP, hugemem kernels, and AMD64, the default is 2048 KB. For Itanium architectures, the default is 262144 KB. This statistic only appears on the x86, Itanium, and AMD64 architectures.
