# workflows

## 1. workflow for build openwrt image

### build a rpi openwrt image
    name: build_rpi_openwrt_image
    run-name: Build a Openwrt image for rpi
    on: workflow_dispatch
    jobs:
      call-docker-build:
        uses: zhenggc1/workflow/.github/workflows/build_openwrt_image.yaml@main
        with:
          openwrt_image: bcm27xx-bcm2708
          openwrt_version: 23.05.2
          openwrt_profile: rpi
          openwrt_root_size: 800

## 2. workflow for build docker image

### build a docker image and upload it to cloudflare
    name: build_alpine_python_image
    run-name: Build a alpine docker image with python
    on: workflow_dispatch
    jobs:
      call-docker-build:
        uses: zhenggc1/workflow/.github/workflows/docker_image.yaml@main
        with:
          docker_file_path: alpine_python
          docker_tag: alpine:python
          docker_image_name: alpine_python
        secrets:
          R2_END_POINT: ${{secrets.R2_END_POINT}}
          R2_ACCESS_KEY_ID: ${{ secrets.R2_ACCESS_KEY_ID }}
          R2_SECRET_ACCESS_KEY: ${{ secrets.R2_SECRET_ACCESS_KEY }}

## 3. workflow for download docker image and package it to a gzip file

### git branch for trigger download docker image

    git branch releases/codercom_code-server_bookworm
    git checkout releases/codercom_code-server_bookworm
    git push -u origin releases/codercom_code-server_bookworm
