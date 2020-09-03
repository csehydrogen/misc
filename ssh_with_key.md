Create public/private key pair.

```bash
$ ssh-keygen -t rsa -b 2048
```

* id_rsa: Private key. Save at local.
* id_rsa.pub: Public key. Save as `.ssh/authorized_keys` at server. `.ssh` should have `700` perm and `.ssh/authorized_keys` should have `600` perm.

```bash
$ ssh -i id_rsa a.b.c.d
```
