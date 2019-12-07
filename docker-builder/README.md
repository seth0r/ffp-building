# Docker FFP-Firmware Builder

Build Freifunk Potsdam (https://freifunk-potsdam.de) images in a Docker container. This is sometimes necessary when building OpenWrt on the host system fails, e.g. when some dependency is too new.

The docker image is based on Debian Linux.
Works with LEDE-17.01, OpenWrt-18.06 and newer.

## Prerequisites

* Docker installed
* running Docker daemon
* build Docker image:

```
git clone https://github.com/seth0r/ffp-building.git
cd ffp-building/docker-builder
docker build -t ffp-builder .
```

Now the docker image is available. These steps only need to be done once.

## Usage

Chechout the firmware and enter the folder,
than execute make in the docker container:
```
git clone https://github.com/Freifunk-Potsdam/firmware.git
cd firmware/
docker run -v "`pwd`:/fw" -it ffp-builder make
```

You can also enter the container with a shell and do whatever you want there:
```
docker run -v "`pwd`:/fw" -it ffp-builder bash
```
