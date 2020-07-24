## Scenario

You have a cluster with a login node (public IP `a.b.c.d`, local IP `192.168.0.1`) and a compute node (local IP `192.168.0.2`).
The login node does not have GPUs, so you setup jupyter notebook server on the compute node.

```bash
$ # On 192.168.0.2
$ jupyter notebook some.ipynb --ip=*
$ netstat -l | grep 8888
tcp        0      0 0.0.0.0:8888            0.0.0.0:*               LISTEN
```

The compute node does not have public IP. How do I access the notebook from an external server?

## Solution

Simple non-sudo apporach is ssh tunneling.

Executing `ssh -L bind:localport:target:targetport remote` on `local` will
* Create a tunnel between `local` and `remote`
* Listen on `bind:localport` at `local`
* Forward packets to `remote`, then to `target:targetport`

Note that `target` is relative to `remote`. If `target` is `localhost`, target server will be the same as remote server.

The following is an example for our scenario.

```bash
$ # On 192.168.0.1
$ ssh -L 0.0.0.0:50080:localhost:8888 192.168.0.2
```

You can connect to the notebook by typing `a.b.c.d:50080` on browser.
