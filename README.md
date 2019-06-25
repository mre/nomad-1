GC-Nomad
=========

<p align="center" style="text-align:center;">
  <img src="https://cdn.rawgit.com/hashicorp/nomad/master/website/source/assets/images/logo-text.svg" width="500" />
</p>

Overview
-------------------------------

This is our twist on Nomad, it has several modifications over the origianl Nomad

* Support in **soft memory limits** - this allows to sensibly distribute load across nodes w/o paying in constant OOM killing


Getting Started
-------------------------------
Follow the instructions to contribute to GC-Nomad

Install `golang` (MacOS/Linux)
==============================
```sh
wget https://dl.google.com/go/go1.12.6.linux-amd64.tar.gz
sudo tar -xvf go1.12.6.linux-amd64.tar.gz
sudo mv go /usr/local
mkdir $HOME/go
export GOROOT=/usr/local/go
export GOPATH=$HOME/go
export PATH=$GOPATH/bin:$GOROOT/bin:$PATH
```
To validate run
```sh
go version
```

GC-Nomad Build node
===================

**Prepare Build Node**
To prepare a VM to be able to build GC-Nomad:
```sh
cd $GOPATH/src/github.com/hashicorp/
git clone https://github.com/zonnie/nomad.git
cd nomad
make bootstrap
```

**Build GC-Nomad**
```sh
go build -o $HOME/nomad
zip -j $HOME/nomad.zip $HOME/nomad
scp $HOME/nomad.zip root@web-server:/storage/nomad/0.9.3/.
```


Contributing to GC-Nomad
------------------------
**Developing locally**
Fetching GC-Nomad
=================
```sh
mkdir $HOME/go/src
cd $HOME/go/src
export $GOPATH=$HOME/go
mkdir $HOME/go/src
cd $HOME/go/src
git clone https://github.com/zonnie/nomad.git
cd nomad
make bootstrap
zip -r $HOME/nomad_src.zip nomad
scp $HOME/nomad.zip root@web-server:/root/go/src/github.com/hashicorp/.
```

