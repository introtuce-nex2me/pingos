# PingOS

[![logo](doc/img/logo-banner-white-400x200.png)](https://pingos.io)

[![website](https://img.shields.io/badge/website-https://pingos.io-red.svg)](https://pingos.io) [![Build Status](https://travis-ci.com/pingostack/pingos.svg?branch=master)](https://travis-ci.com/pingostack/pingos) [![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)


 > [PingOS](https://pingos.io/docs/zh/quick-start) dependent [NGINX](https://github.com/nginx/nginx) constructed and inherits [arut](https://github.com/arut/nginx-rtmp-module) and [AlexWoo](https://github.com/AlexWoo/nginx-rtmp-module) of nginx-rtmp-module module. In addition to fixing some of the problems in the arut and AlexWoo versions, PingOS has made several functional extensions in encoding and live broadcast protocols and other aspects.


---

# Server function

- [x] **Live broadcast protocol:** RTMP, HTTP (S) -FLV, HTTP (S) -TS, HLS (support HTTPS), HLS + (support HTTPS), DASH (support HTTPS).
- [x] **Audio and video coding:**  H264, H265, MP3, AAC.
- [x] **Live video:** FLV file format and TS file format.
- [x] **GOP cache: to** achieve second open and memory reuse.
- [x] **Application supports wildcards:**  wildcards can automatically match the application name used in the push-pull flow, without cumbersome configuration.
- [x] **VHOST function:** support to configure multiple server domain names.
- [x] **Console interface:** Control the push, pull, and recording processes through the HTTP API interface.
- [x] **Configuration dynamic loading: After** modifying the configuration file, the latest configuration can be read without any operation on nginx.
- [x] **Flow accounting:** By configuring custom flow logs.
- [x] **Variable parameter configuration:** Variables are used in the configuration file.
- [x] **Back-to-source** between processes : Pulling flows between processes solves the problem that the native nginx-rtmp-module module fails to pull flows in multiple processes.
- [x] **Clustering function:** push-pull streaming function between servers (http-flv, rtmp protocol).
- [x] **html5 web player: The** [pingos-player](https://github.com/pingostack/pingos-player)player will continue to be compatible with various browser platforms and multiple live broadcast protocols.

# Guide

- [Project documentation](https://pingos.io/docs/zh/quick-start)

## Quick installation

- [Use Docker image](docker/README.md)

- Install directly into the system
    ```bash
   # Quick Installation
    git clone https://github.com/pingostack/pingos.git

    cd pingos

    ./release.sh -i

   
    # Start the service 
    cd /usr/local/pingos/
    ./sbin/nginx
    ```

## Instructions

### Push flow

Push stream address: rtmp://ip/live/stream_name

### Play address

- rtmp playback: rtmp://ip/live/stream_name

- http (s) -flv playback: http (s)://ip/flv/stream name

- hls play: http (s)://ip/hls/stream_name.m3u8

- hls + play:http (s)://ip/hls2/ stream_name.m3u8
- http (s) -ts play: http (s)://ip/ts/stream_name

### Live stream monitoring background

> Access address: http://ip/rtmp_stat Through this page, you can view the current push and playback records.

> html5 player


### html5 player

> Access address: http://ip/h5player/flv This player is a web-based player based on flv.js, which can implement http-flv live streaming without plug-ins. Once you can access this page, it means that your live broadcast server has been successfully set up.


![h5player](doc/img/flvplayer.png)
<div class="article__content" markdown="1">
