
---
title: 集成客户端
description: 
platform: Web
updatedAt: Wed Nov 07 2018 09:56:15 GMT+0000 (UTC)
---
# 集成客户端
本文介绍在正式使用 Agora Web SDK 进行音视频通话前，需要准备的开发环境，包含前提条件及 SDK 集成方法等内容。

## 前提条件

1. 查看下表安装一款 Agora Web SDK 支持的浏览器。
  <table>
  <tr>
    <th>平台</th>
    <th>Chrome 58+</th>
    <th>Firefox 56+</th>
    <th>Safari 11+</th>
    <th>Opera 45+</th>
    <th>QQ 浏览器最新版</th>
    <th>360 安全浏览器</th>
    <th>微信浏览器</th>
  </tr>
  <tr>
    <td>Android 4.1+</td>
    <td><font color="green">✔</td>
    <td><font color="green">✔</td>
		<td><b>N/A</b></td>
    <td><font color="red">✘</td>
    <td><font color="red">✘</td>
    <td><font color="red">✘</td>
    <td><font color="red">✘</td>
  </tr>
  <tr>
    <td>iOS 11+</td>
    <td><font color="red">✘</td>
    <td><font color="red">✘</td>
    <td><font color="green">✔</td>
    <td><font color="red">✘</td>
    <td><font color="red">✘</td>
    <td><font color="red">✘</td>
    <td><font color="red">✘</td>
  </tr>
  <tr>
    <td>macOS 10+</td>
    <td><font color="green">✔</td>
    <td><font color="green">✔</td>
    <td><font color="green">✔</td>
    <td><font color="green">✔</td>
    <td><font color="green">✔</td>
    <td><font color="red">✘</td>
    <td><font color="red">✘</td>
  </tr>
  <tr>
    <td>Windows 7+</td>
    <td><font color="green">✔</td>
    <td><font color="green">✔</td>
		<td><b>N/A</b></td>
    <td><font color="green">✔</td>
    <td><font color="green">✔</td>
    <td><font color="green">✔</td>
    <td><font color="red">✘</td>
  </tr>
</table>

> Agora Web SDK 2.5 还支持 Windows XP 平台的 Chrome 49 版本。

2. 请确保已打开特定端口，详见 [防火墙说明](../../cn/Agora%20Platform/firewall.md) 。
3. 请确保你已知悉发版说明中列出的问题，详见 [已知问题和局限](../../cn/Voice/release_web_video.md) 及 [常见问题回答](../../cn/Voice/websdk_related_faq.md)。

## 创建 Agora 账号并获取 App ID

1. 进入 [https://dashboard.agora.io/](https://dashboard.agora.io/) ，按照屏幕提示创建一个开发者账号。
2. 登陆 Dashboard 页面，点击 **添加新项目**。

	<img alt="../_images/appid_1.jpg" src="https://web-cdn.agora.io/docs-files/cn/appid_1.jpg" />

1. 填写 **项目名**，然后点击 **提交**。
2. 在你创建的项目下，查看并获取该项目对应的 **App ID**。

	<img alt="../_images/appid_2.jpg" src="https://web-cdn.agora.io/docs-files/cn/appid_2.jpg" />



## 获取 Agora Web SDK 安装包并保存到项目下

选择如下任意一种方法获取 Agora Web SDK，并保存在你所工作的项目下：

### 方法 1. 使用 npm 获取安装包

使用该方法需要先安装 npm，详见[ npm 快速入门](https://www.npmjs.com.cn/getting-started/installing-node/)。

1. 运行安装命令
  `npm install agora-rtc-sdk`

	
2. 在你的项目文件开头添加以下代码

	```javascript
	import AgoraRTC from 'agora-rtc-sdk'
	```

### 方法 2. 使用 CDN 方法获取安装包

该方法无需在官网下载安装包。在项目相应的前端页面文件中，将如下代码添加到 `</body>` 上一行：


	```javascript
	<script src="http://cdn.agora.io/sdk/web/AgoraRTCSDK-2.4-latest.js"></script>
	```


### 方法 3. 从官网获取安装包

1. 从 Agora 官方网站 [下载](https://docs.agora.io/cn/Agora%20Platform/downloads) 最新版 Agora Web SDK 软件包。

	<img alt="../_images/web_sdk_download.png" src="https://web-cdn.agora.io/docs-files/cn/web_sdk_download.png" style="width: 500px"/>

2. 将下载下来的软件包中的 `AgoraRTCSDK-2.3.1.js` 文件保存到你所操作的项目下。
3. 在项目相应的前端页面文件中，对 `AgoraRTCSDK-2.3.1.js` 进行引用。

	<img alt="../_images/web_sdk_reference.jpg" src="https://web-cdn.agora.io/docs-files/cn/web_sdk_reference.jpg" />

> 此处的截图仅供参考，安装时请使用最新版的 SDK 和链接地址。

## 准备网页服务器

1. 安装本地网页服务器，如 Apache、 Nginx 或 Node.js 等。
2. 将下载下来的 Agora Web SDK 部署到网页服务器上。
3. 在网页服务器上用浏览器打开示例程序页面或者你自己创建的页面。

你已经完成了客户端集成，可以开始使用 Agora SDK 了。
