## Enabling hugepage on Centos 7

```bash
$ vim /etc/default/grub
(Add "default_hugepagesz=1G hugepagesz=1G hugepages=4 hugepagesz=2M hugepages=1024" at the end of GRUB_CMDLINE_LINUX)
$ grub2-mkconfig -o /boot/grub2/grub.cfg
$ reboot

$ # Check
$ grep Huge /proc/meminfo
$ cat /sys/kernel/mm/hugepages/hugepages-2048kB/nr_hugepages
$ cat /sys/kernel/mm/hugepages/hugepages-1048576kB/nr_hugepages

$ # Adjusting
$ echo 20 > /sys/kernel/mm/hugepages/hugepages-2048kB/nr_hugepages
$ echo 2 > /sys/kernel/mm/hugepages/hugepages-1048576kB/nr_hugepages
```
