gnu global
====

## prepare

```sh
$ pip install Pygments
$ apt install exuberant-ctags
$ set -gx GTAGSLABEL pygments
```


## install

see http://www.gnu.org/software/global/download.html

```sh
$ tar xvf global-{VERSION}.tar.gz
$ cd global-{VERSION}
$ ./configure
$ make
$ sudo make install
```

## check

```sh
$ gtags --debug
library: |*/pygments-parser.la|
```
