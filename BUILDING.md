*Under construction*

For now, you can follow [WLinux building guide](https://github.com/WhitewaterFoundry/Pengwin/blob/master/BUILDING.md), except how to make the install.tar.gz. See below

# How to make install.tar.gz

The easiest way to make the tarball (for me) is to use docker image. If you have docker installed, you can do:
```bash
docker pull cern/cc7-base
docker run --name cc7-wsl cern/cc7-base bash -c "yum install -y passwd sudo && yum clean all"
docker export cc7-wsl | gzip > install.tar.gz
```
If you don't have docker, you can use something like [WSL-Distribution-Switcher](https://github.com/RoliSoft/WSL-Distribution-Switcher) to download the tarball. The only caveat is that you may have to remake it to make sure that the content of rootfs is at the root of the tarball and not inside another directory.