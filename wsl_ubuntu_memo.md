WSL (Windows Subsystem for Linux)
====

## apt mirror repository
/etc/apt/sources.list.d/iij.list

```sh
deb http://ftp.iij.ad.jp/pub/linux/ubuntu/archive/ xenial main restricted universe multiverse
deb http://ftp.iij.ad.jp/pub/linux/ubuntu/archive/ xenial-updates main restricted universe multiverse
deb http://ftp.iij.ad.jp/pub/linux/ubuntu/archive/ xenial-backports main restricted universe multiverse
deb http://ftp.iij.ad.jp/pub/linux/ubuntu/archive/ xenial-security main restricted universe multiverse
```

/etc/apt/sources.list.d/jaist.list

```sh
deb http://ftp.jaist.ac.jp/pub/Linux/ubuntu/ xenial main restricted universe multiverse
deb http://ftp.jaist.ac.jp/pub/Linux/ubuntu/ xenial-updates main restricted universe multiverse
deb http://ftp.jaist.ac.jp/pub/Linux/ubuntu/ xenial-backports main restricted universe multiverse
deb http://ftp.jaist.ac.jp/pub/Linux/ubuntu/ xenial-security main restricted universe multiverse
```

/etc/apt/sources.list

```diff
- deb http://archive.ubuntu.com/ubuntu/ xenial main restricted universe multiverse
- deb http://archive.ubuntu.com/ubuntu/ xenial-updates main restricted universe multiverse
  deb http://security.ubuntu.com/ubuntu/ xenial-security main restricted universe multiverse

+ #deb http://archive.ubuntu.com/ubuntu/ xenial main restricted universe multiverse
+ #deb http://archive.ubuntu.com/ubuntu/ xenial-updates main restricted universe multiverse
  deb http://security.ubuntu.com/ubuntu/ xenial-security main restricted universe multiverse
```

## gcc

```sh
$ sudo apt-get update
$ sudo apt-get install build-essential software-properties-common -y
$ sudo add-apt-repository ppa:ubuntu-toolchain-r/test -y
$ sudo apt-get update
$ sudo apt-get install gcc-snapshot -y
$ sudo apt-get update
$ sudo apt-get install gcc-6 g++-6 -y
$ sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-6 60 --slave /usr/bin/g++ g++ /usr/bin/g++-6
$ sudo apt-get install gcc-4.8 g++-4.8 -y
$ sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-4.8 60 --slave /usr/bin/g++ g++ /usr/bin/g++-4.8

$ sudo update-alternatives --config gcc

$ gcc -v
```


## pyenv in fish

```sh
$ sudo apt install 
```

$HOME/.config/fish/config.fish

```sh
set -gx PYENV_ROOT "$HOME/.pyenv"
set -x PATH $PATH "$PYENV_ROOT/bin"
status --is-interactive; and source (pyenv init - | psub)
status --is-interactive; and source (pyenv virtualenv-init - | psub)

```

$ sudo apt-get install software-properties-common
$ sudo apt-get install python-software-properties

pyenv install anaconda3-4.2.0
pyenv global anaconda3-4.2.0

cd $XDG_CONFIG/fish/functions
ln -s (conda info --root)/etc/fish/conf.d/conda.fish

