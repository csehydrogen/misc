## Cannot boot into USB installer

* Turn on "Above 4G Decoding" option in BIOS

## Fail during install

* Check system time
  ```bash
  $ date # check if system time is too old
  Wed Nov 21 11:36:20 UTC 2018
  $ sudo date --utc --set "Wed Nov 21 16:37:00 UTC 2018" # set to current time
  $ sudo hwclock --systohc # ???
  ```
  * https://bugs.launchpad.net/ubuntu/+bug/1779757
