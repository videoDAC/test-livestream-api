![test1](https://user-images.githubusercontent.com/2212651/83407753-04d97600-a42f-11ea-9aab-33e45d84f038.gif)

# `test-livestream-api`

This repository contains information about videoDAC's test-livestream API.

# Contents

- [Objective](#objective)
- [About](#about)
- [Public API](#public-api)
- [Local API](#local-api)
- [Connect to API](#connect-to-api)
  - [Command Line Interface](#command-line-interface)
  - [Graphical User Interface](#graphical-user-interface)
  - [Web Interface](#web-interface)
  - [Mobile SDK](#mobile-sdk)
  
# Objective

To help developers of video-enabled applications start developing client applications for Consuming livestreaming video.

## About

videoDAC's test-livestream API is a one-way livestream of AV (audiovisual) content.

> _The content is of a dynamic multi-coloured test card including an integer which increments every one second._

It is presented as a [`.m3u8`](https://en.wikipedia.org/wiki/M3U) file extension, and contains a stream of [`hls`](https://en.wikipedia.org/wiki/HTTP_Live_Streaming) AV segments.

The content is in `144p` format, which is 256 pixels by 144 pixels, refreshing at a rate of 30 frames per second.

This is a `gif` file showing a sample of the content:

![test](https://user-images.githubusercontent.com/2212651/83393535-95ef2380-a414-11ea-98b7-9c3babad46ac.gif)

## Public API

A publicly-available API is provided as a free-to-use hosted-service at the following URL:

[http://52.29.226.43:8935/stream/hello_world.m3u8](http://52.29.226.43:8935/stream/hello_world.m3u8)

```
http://52.29.226.43:8935/stream/hello_world.m3u8
```

## Local API

To set up your own local API, go to [`simple-streaming-server`](https://github.com/videoDAC/simple-streaming-server).

## Connect to API

Instructions for connecting to the API using a [`Command Line Interface`](#command-line-interface) or a [_Graphical User Interface_](#graphical-user-interface).

### `Command Line Interface`

#### `curl` (content meta-data only)

This requires `curl` to be installed on your system:

1. Open `Terminal`.

2. Run this command to Consume content meta-data from the test livestream API:
```
curl http://52.29.226.43:8935/stream/hello_world.m3u8
```

3. View content meta-data:
![image](https://user-images.githubusercontent.com/2212651/83391694-79052100-a411-11ea-90e4-609dae3295b0.png)

#### `ffplay` (`FFmpeg`)

This requires [`FFmpeg`](https://ffmpeg.org/) to be installed on your system:

1. Open `Terminal`.

2. Run this command to Consume content from the test-livestream API:
```
ffplay http://52.29.226.43:8935/stream/hello_world.m3u8
```

3. View content being played:

![image](https://user-images.githubusercontent.com/2212651/83391361-fa0fe880-a410-11ea-89e1-3b74c6e9447f.png)

### Graphical User Interface

### VLC Media Player

This requires [VLC Media Player](https://www.videolan.org/vlc/index.html) to be installed on your system.

VLC Media Player is available on Android, iOS, Windows, Linux and MacOS.

1. Open VLC Media Player

![image](https://user-images.githubusercontent.com/2212651/83395488-05b2dd80-a418-11ea-9b3c-647389e3911b.png)

2. Open Network Stream (Ctrl+n) and paste the URL for the API into the field:

![image](https://user-images.githubusercontent.com/2212651/83395456-ef0c8680-a417-11ea-8ba0-3484b333d89a.png)

3. Press Play, and view the content

![image](https://user-images.githubusercontent.com/2212651/83395802-9093d800-a418-11ea-946f-f8f6d2b04281.png)

### OBS Studio

This requires [OBS Studio](https://obsproject.com/) to be installed on your system. OBS Studio is available on Windows, Linux and MacOS.

1. Open OBS Studio

![image](https://user-images.githubusercontent.com/2212651/83397458-47915300-a41b-11ea-9254-7e966f56bd9a.png)

2. Add a new "Media Source" under "Sources"

![image](https://user-images.githubusercontent.com/2212651/83397513-609a0400-a41b-11ea-957b-2a3614e6a902.png)

3. Deselect "Local File", and paste the URL for the API into the "Input" field:

![image](https://user-images.githubusercontent.com/2212651/83404312-12d7c880-a428-11ea-9f9a-7fc4c84f77f8.png)

4. Click "OK" and see the content as a new Source in OBS:

![image](https://user-images.githubusercontent.com/2212651/83404403-3a2e9580-a428-11ea-8099-e0ab4f7bbc60.png)

### Web Interface

#### `hls.js` player

[`hls.js`](https://github.com/video-dev/hls.js/) is a Javascript library for displaying `hls` video content.

Here is [a sample html page containing hls.js player](/www/hosted-test-api-player.html), playing content from the hosted test-livestream-api URL.

Alternatively, you can [get started using `hls.js` documentation](https://github.com/video-dev/hls.js/#getting-started).

### Mobile SDKs

#### Android (ExoPlayer)

[ExoPlayer](https://exoplayer.dev/) is an application level media player for Android.
