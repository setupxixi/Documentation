
---
title: 产品概述
description: 
platform: All Platforms
updatedAt: Fri Nov 09 2018 11:02:03 GMT+0000 (UTC)
---
# 产品概述
Agora 视频通话可以实现一对一、一对多的音视频通话，提供极致的流畅体验和低延时互动效果，适用于各种视频社交和在线教育场景。

Agora 视频通话和[互动直播](https://docs.agora.io/cn/Interactive%20Broadcast/product_live?platform=All%20Platforms)的主要区别是，视频通话不区分用户角色，所有用户都可以自由发言，默认流畅和低延时优先，一个典型场景是多人视频会议；互动直播中用户分为主播和观众，只有主播可以自由发言，默认高画质优先，一个典型场景是直播答题。

## 功能和场景

Agora 视频通话提供丰富的功能，你可以根据自己的场景需求灵活组合。

| 主要功能             | 功能描述                                                     | 典型适用场景                                                 |
| -------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 伴奏混音             | 将本地或在线的音频和用户声音，同时发送并播放给频道内其他用户 | <li>在线合唱 <li>针对幼儿的音乐互动课堂                      |
| 屏幕分享             | 把屏幕内容同步展示给频道内的其他用户                         | 互动课堂                                                     |
| 修改音视频原始数据   | 可支持变声，支持获取媒体引擎的原始语音或视频数据，对原始数据进行处理 | <li>聊天室变声<li>视频聊天美颜                           |
| 自定义视频源和渲染器 | 支持自定义的视频源和渲染器，可以不使用系统摄像头，使用自己构建的 camera 视频源，屏幕共享视频源，或者文件视频源等，可以更灵活地处理视频，比如添加美颜效果、滤镜等。 | <li>需要使用自定义的美颜库或者前处理库<li>开发者 App 中已经有自己的图像视频模块<li>开发者希望使用非 Camera 的视频源，比如录屏数据<li>有些系统独占的视频采集设备，为了避免与其他业务冲突，需要灵活的设备管理策略。 |

## 关键特性

| 特性         | Agora 视频通话指标                                           |
| ------------ | ------------------------------------------------------------ |
| SDK 包体积   | 3.69 M - 7.75 M                                              |
| 多人视频     | 支持 7 人视频通话（如需更多人数，可以使用 [Agora 互动直播](https://docs.agora.io/cn/Interactive%20Broadcast/product_live?platform=All%20Platforms)） |
| 视频属性     | <li>SDK 采集支持 1080p 分辨率，60 fps 帧率 <li>自采集支持 4K |
| 音频属性     | <li>音频采样率：16 KHz - 48 KHz <li>支持单、双声道           |
| 音频抗丢包率 | 上下行抗丢包率 70%                                           |

### 平台兼容

视频通话支持 iOS、Android、Windows、macOS、Linux、Web、小程序，并支持平台间互通，具体的兼容性要求见下表。

| 平台       | 支持版本                                                     |
| ---------- | ------------------------------------------------------------ |
| Android    | 4.1+                                                         |
| iOS        | 8.0+                                                         |
| Windows    | XP SP3+                                                      |
| macOS      | 10.0+                                                        |
| 微信小程序 | 支持                                                         |
| Web        | <li>Chrome 58+ <li>Firefox 56+ <li>Safari 11+ <li>Opera 45+ <li>QQ 10+ <li>360 安全浏览器 9.1+ |

## Demo 体验

### 视频通话应用 - Agora Video Call

在应用市场下载 Agora Video Call app，快速体验多人跨国视频通话。

- [Android](http://android.myapp.com/myapp/detail.htm?apkName=io.agora.vcall)
- [iOS](https://itunes.apple.com/cn/app/agora-video-call/id1080303824)
- [macOS](https://itunes.apple.com/cn/app/agora-video-call/id1112106913)
- [Web](https://webdemo.agora.io/videocall/?_ga=2.212778772.1474390666.1541382528-1513744824.1530171825)
- [Windows](http://download.agora.io/avc/AgoraVideoCall_for_windows_2.2.0.zip?_ga=2.212778772.1474390666.1541382528-1513744824.1530171825)
