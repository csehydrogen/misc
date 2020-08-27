```bash
$ lspci | grep RAID
02:00.0 RAID bus controller: LSI Logic / Symbios Logic MegaRAID SAS-3 3108 [Invader] (rev 02)
```

Go to https://www.broadcom.com/support/download-search and search megacli. Download it and install.

```bash
$ alias megacli='/opt/MegaRAID/MegaCli/MegaCli64'
$ megacli -LdPdInfo -a0
...
Enclosure Device ID: 0
Slot Number: 9
...
Firmware state: Failed
...
```
