---
layout: posts
title: FFmpeg 备忘
---


# 常用命令

## 以 192k 码率提取 FLV 视频格式中的音频为 MP3 格式

```bash
$ ffmpeg -i video.flv -ab 192k audio.mp3
```

- MP3 音频格式的码率在 192k ~ 320k 为佳, 320k 为最高码率.
- 不添加码率参数时, 默认码率为 124k.




## 音频为 AAC 格式的 FLV 视频提取原音频

```bash
$ ffmpeg -i video.flv -acodec copy audio.aac
```


## FLV 视频格式提取位于 00:00:01 的一帧为 PNG 图片格式

```bash
$ ffmpeg -ss 00:00:01 -i video.flv -vframes 1 frame.png
```



## TS 视频格式转 MP4 视频格式

```bash
$ ffmpeg -i input.ts -acodec copy -vcodec copy -f mp4 output.mp4
```



## 剪辑视频从 00:00:10 到 00:00:35

```bash
$ ffmpeg -ss 00:00:20 -i video.mkv -t 00:00:25 -c copy output.mkv
```

- 参数 -t 用于指定结束时长(需要减去片头), 不加表示去除片头.
- Try `-avoid_negative_ts 1` as a possible workaround.

