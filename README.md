# workflows

## 0. howto using
> workflow read a file in this repository as config an run on config file push.

## 1. workflow for build openwrt image

### build a rpi openwrt image, read a config file on directory openwrt_build, here is a example openwrt_build/rpi.env
```
openwrt_image= bcm27xx-bcm2708
openwrt_version= 23.05.2
openwrt_profile= rpi
openwrt_root_size= 800
```

## 2. workflow for build docker image

### build a docker image and upload it to cloudflare, read a config file on directory docker_build, here is a example docker_build/alpine_local.env
```
docker_file_path= docker_build/alpine_python
docker_tag= alpine:python
docker_image_name= alpine_python
```

## 3. workflow for download docker image and package it to a gzip file

### git branch for trigger download docker image,read a config file on directory docker_download, here is a example docker_download/alpine_local.env
```
tag_name=alpine:latest
pkg_name=alpint_latest
```
