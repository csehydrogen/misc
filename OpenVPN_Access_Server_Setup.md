## Install

```bash
yum -y install https://as-repository.openvpn.net/as-repo-centos7.rpm
yum -y install openvpn-as
```

## Account

`openvpn` account will be created on the server. Set password with `passwd`.

## Troubleshoot

By default, `# cpu cores` daemons will be created for tcp and udp.
This may cause port depletion on a server with lots of CPU cores.
Reduce the number of daemons with the following:

```bash
cd /usr/local/openvpn_as/scripts
./sacli ConfigQuery # check config
./sacli --key "vpn.server.daemon.tcp.n_daemons" --value "2" ConfigPut # reduce tcp daemon to 2
./sacli --key "vpn.server.daemon.udp.n_daemons" --value "2" ConfigPut # reduce udp daemon to 2
./sacli start
```

## Port Change

``` bash
./sacli --key "vpn.server.daemon.tcp.port" --value 50443 ConfigPut
./sacli --key "vpn.server.daemon.udp.port" --value 51194 ConfigPut
./sacli start
```
