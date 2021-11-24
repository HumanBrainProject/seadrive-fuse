# seadrive-fuse
Fork of SeaDrive daemon with FUSE interface with custom config options

# Additional Config options
## Default Repo
The default repo will be initialized and synchronized first. This can be useful when using the daemon in an application where there is a specific repo that is referenced and startup time is important

The config option can be set in the existing config file under:
```
[repo]
default_repo=Repo name goes here
```

# Building
## Ubuntu Linux
```
sudo apt-get install autoconf automake libtool libevent-dev libcurl4-openssl-dev libgtk2.0-dev uuid-dev intltool libsqlite3-dev valac libjansson-dev libssl-dev
```

First, you shoud get the latest source of [libsearpc](https://github.com/haiwen/libsearpc) with `v3.2-latest` tag and [seadrive-fuse](https://github.com/haiwen/seadrive-fuse).

To build [seadrive-fuse](https://github.com/haiwen/seadrive-fuse), you need first build [libsearpc](https://github.com/haiwen/libsearpc).
### libsearpc
```
git clone --branch=v3.2-latest https://github.com/haiwen/libsearpc.git
cd libsearpc
./autogen.sh
./configure
make
sudo make install
```
### seadrive-fuse
```
git clone https://github.com/haiwen/seadrive-fuse.git
cd seadrive-fuse
./autogen.sh
./configure
make
sudo make install
```

**Note:** If you plan to package for distribution, you should compile with the latest tag instead of the master branch. Sometimes the latest tag for seadrive-gui project (https://github.com/haiwen/seadrive-gui) is higher than the tag here. In such case you should follow the tag in this project. For example, the latest tag for seadrive-fuse is v2.0.6 while for seadrive-gui is v2.0.7. You should build the package based on v2.0.6 tag from seadrive-gui too. This is because sometimes there is no update related to Linux in the new versions so this project is not updated.
