
---
title: 实现语音直播
description: 
platform: Android
updatedAt: Tue Oct 16 2018 10:26:22 GMT+0000 (UTC)
---
# 实现语音直播
# 实现语音直播

在本页你可以了解如何使用 Agora SDK 实现语音直播。

## 准备环境

1.  关于具体的开发环境要求、如何获取 App ID 以及 SDK 集成方法，详见 [设置开发环境](../../cn/Quickstart%20Guide/android_video.md) 。

2.  参考 [OpenLive Voice Only for Android](https://github.com/AgoraIO/Basic-Audio-Broadcasting/tree/master/OpenLive-Voice-Only-Android) 了解如何从头创建一个实例项目。


## 快速开始

### 创建实例

导入以下 Agora API 包:

-   `io.agora.rtc.Constants`
-   `io.agora.rtc.IRtcEngineEventHandler`
-   `io.agora.rtc.RtcEngine`


进入直播频道之前，调用 `create` 创建一个实例。在该方法中:

-   填入 [设置开发环境](../../cn/Quickstart%20Guide/android_video.md) 里获取到的 App ID。只有 App ID 相同的应用程序才能进入同一个频道进行互通。
-   指定一个事件回调。SDK 通过指定的事件通知应用程序 SDK 的运行事件，如: 加入或离开频道，新用户加入频道等。


```
import io.agora.rtc.Constants;
import io.agora.rtc.IRtcEngineEventHandler;
import io.agora.rtc.RtcEngine;


...

private void initializeAgoraEngine() {
    try {
        mRtcEngine = RtcEngine.create(getBaseContext(), getString(R.string.agora_app_id), mRtcEventHandler);
    } catch (Exception e) {
        Log.e(LOG_TAG, Log.getStackTraceString(e));

        throw new RuntimeException("NEED TO check rtc sdk init fatal error\n" + Log.getStackTraceString(e));
    }
}
```

### 设置频道模式

创建实例后，调用 `setChannelProfile` 方法设置频道模式。SDK 会根据所设置的频道模式使用不同的优化手段。 
在该方法中，将频道模式设置为直播模式。直播模式适用于互动直播场景。频道内有主播和观众两种角色，主播收发语音消息，观众只收不发。

> - 该方法必须在加入频道前调用才能生效。
> - 同一频道只能设置一种频道模式。如果需要切换频道模式，请先调用 `destroy` 方法销毁后重新创建一个 Engine 实例，再调用该方法将频道设置为其他模式。


```
mRtcEngine.setChannelProfile(Constants.CHANNEL_PROFILE_LIVE_BROADCASTING);
```

### 设置用户角色

直播频道分主播和观众两种用户角色。在将频道模式为直播后，调用 `setClientRole` 方法，并根据需要将用户设置为主播或观众。两者的区别在于：

-   主播：可以收听和发布音频消息。根据应用程序的实现，还可以与观众互动、指定观众连麦。同一直播频道内，主播只能听到自己以及连麦主播的音频。
-   观众：只能收听主播的音频消息。根据应用程序的实现，还可以发布实时文字消息，与主播互动。同一直播频道内，所有观众都能听到主播以及连麦主播的音频。

> 在加入直播频道前，务必调用该方法设置用户角色。直播过程中，用户也可以再次调用该方法，改变设置的用户角色。

```
mRtcEngine.setClientRole(Constants.CLIENT_ROLE_BROADCASTER)
```

### 加入频道

现在你可以加入直播频道了。调用 `joinChannel` 方法加入频道。同一个频道内的主播可以互相通话，观众可以收听主播。

-   传入能标识用户角色和权限的 Token。如果安全要求不高，也可以将值设为 null。Token 需要在应用程序的服务器端生成，具体生成办法，详见 [密钥说明](../../cn/Agora%20Platform/token.md)。
-   传入能标识频道的频道 ID。输入相同频道 ID 的用户会进入同一个频道。
-   频道内每个用户的 UID 必须是唯一的。如果将 UID 设为 0，系统将自动分配一个 UID。

> 如果已在频道中，用户必须调用 `leaveChannel` 方法退出当前频道，才能进入下一个频道。

```
 private void joinChannel() {
    mRtcEngine.joinChannel(null, "demoChannel1", "Extra Optional Data", 0); // if you do not specify the uid, Agora will assign one.
}
```

### 结束/退出直播

调用 `leaveChannel` 方法离开频道，结束或退出直播。

不论当前是否还在直播中，调用该方法会把直播相关的所有资源释放掉。`leaveChannel` 并不会直接让用户离开频道。调用该方法后 SDK 会触发 `onLeaveChannel` 回调。

```
 private void leaveChannel() {
    mRtcEngine.leaveChannel();
}
```

> 如果在调用 `leaveChannel` 方法后立即使用 `destroy`，则退出频道会被打断，SDK 也不会触发 `onLeaveChannel` 回调。

### 结论

现在你可以开始直播了。

## 参考

在上述语音直播过程中，我们使用了 Agora SDK 提供的部分 API 功能：

-   创建 RtcEngine 对象：`create`
-   设置频道属性：`setChannelProfile`
-   设置用户角色：`setClientRole`
-   加入频道：`joinChannel`


在实现语音直播的过程中，你还可能需要使用以下功能:

-   [实现客户端连麦](../../cn/Quickstart%20Guide/hostin_android.md)
-   [实现跨直播间连麦](../../cn/Quickstart%20Guide/hostin_crosschannel_android.md)
-   [推流到 CDN](../../cn/Quickstart%20Guide/push_stream_android.md)
-   [录制音视频](../../cn/Quickstart%20Guide/recording_voice_video.md)
-   [选择加密方案](../../cn/Quickstart%20Guide/encryption_android_agora.md)
-   [修改裸数据](../../cn/Quickstart%20Guide/rawdata_android.md)

更多功能实现，请参考 [互动直播 API](https://docs.agora.io/cn/Interactive%20Broadcast/API%20Reference/java/index.html) 中各 API 的功能及描述。

