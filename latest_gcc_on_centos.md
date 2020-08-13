```bash
$ git clone --depth 1 --branch releases/gcc-8.4.0 git://gcc.gnu.org/git/gcc.git
$ cd gcc
$ ./contrib/download_prerequisites
$ yum install glibc-devel.i686 libgcc.i686 flex
$ mkdir $HOME/local
$ ./configure --prefix=$HOME/local
$ make -j
$ make install
```
