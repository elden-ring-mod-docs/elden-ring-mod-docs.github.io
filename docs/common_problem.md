---
title: 常见问题
nav_order: 4
---

<details open markdown="block">
  <summary>
    目录
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---

# Steam is not launched.

{: .note-title }
> 中文意思是
> 
> steam未启动

> 常见于学习版steam无缝联机玩家

![steam未启动.png](/assets/images/steam未启动.png)

1. 如果steam没有启动，那就启动steam，再启动游戏
1. 如果已经启动steam了，那就右键管理员启动游戏

---

# Unsupported SteamUser version! SteamUser023
> 常见于学习版steam无缝联机

![不支持的steam用户版本.png](/assets/images/不支持的steam用户版本.png)

出现这个情况是因为你游戏目录里的`OnlineFix64.dll`这个文件不是联机补丁里面的(不知道哪搞来的)，正确的联机补丁这个文件应该是`11,582 KB`

解决方案就是找到联机补丁里的这个文件重新覆盖进去

参考：[安装无缝联机，如果你是学习版需要额外打一个联机补丁]({{site.baseurl}}/docs/upgrade/esrc/#如果你是学习版需要额外打一个联机补丁)

---

# Failed to find "SeamlessCoop//ersc.dll" (Error = 2)

![ersc_dll文件丢失.png](/assets/images/ersc_dll文件丢失.png)

如图所示，你这个文件丢了，这个是无缝联机mod的其中一个文件，找一下放进去就行了

参考：[安装无缝联机]({{site.baseurl}}/docs/upgrade/esrc/)

---

# Please enter a session password in your settings file.

{: .note-title }
> 中文意思是
> 
> 请在配置文件中设置一个房间密码（会话密码）

这个是无缝联机mod的提示，提示你需要设置一个房间密码才能启动游戏，在无缝的配置文件`ersc_settings.ini`里设置一下房间密码就行了

![无缝没设置密码.png](/assets/images/无缝没设置密码.png)

设置密码步骤参考：[安装无缝联机]({{site.baseurl}}/docs/upgrade/esrc/)

---

# This version of seamless co-op (1.x.x) is depreciated and requires an update.

{: .note-title }
> 中文意思是
> 
> 当前版本的无缝联机mod已经被弃用，需要更新到最新版

![无缝不是最新版.png](/assets/images/无缝不是最新版.png)

如图所示 图片中出现的1.7.2就是代表当前版本，需要下载最新版覆盖进去就行了

下载最新版无缝参考：[安装无缝联机]({{site.baseurl}}/docs/upgrade/esrc/)

---

# Failed to load dll from the list. 或者 WaitForSingleObject failed! Return value = 258, Error = 0

{: .note-title }
> 中文意思是
> 
> 从列表中加载dll文件失败

> 常见于学习版steam无缝联机

![dll文件未找到.png](/assets/images/dll文件未找到.png)

找到游戏目录中的`dlllist.txt`文件,并打开

![dlllist文件.png](/assets/images/dlllist文件.png)

![dlllist文件内容.png](/assets/images/dlllist文件内容.png)

确保文件中涉及到的dll文件都存在，最常见的就是`OnlineFix64.dll`文件被杀毒软件删了，
需要加一下白名单，把这个文件重新拖进来，不知道如何操作可以参考这个空降链接：
[法魂mod兼容无缝教程(含正版学习版)-授人以渔 【精准空降到 45:17】](https://www.bilibili.com/video/BV1cLieYtE5d/?t=2717){:target="_blank"}

我这里只有一个dll，所以只需要确认这一个dll文件是否存在，如果你有多个，需要依次确认是否存在

还有一点就是**不要有空行**，空行也会被认为是一个dll文件，导致报错

![dlllist文件空行示范.png](/assets/images/dlllist文件空行示范.png)
❌错误示范

如果你没有空行，涉及的dll文件也都存在，那就把涉及到的dll文件再重新覆盖一遍

---

# 打上无缝联机mod之后手柄没有反应？

> 常见于学习版steam无缝联机

找到steam库中的`spacewar`，右键-属性-控制器-禁用steam输入，如果还不行，就在`控制器配置器`里选一个steam映射
![禁用steam输入.png](/assets/images/禁用steam输入.png)

---

# 游戏版本与保存数据不相符。请结束游戏，从Steam客户端更新版本后，重新启动游戏

![游戏版本与保存数据不相符.jpg](/assets/images/游戏版本与保存数据不相符.jpg)

这个提示是因为存档的版本高于游戏的版本，解决方案有两个，二选一即可
1. 升级游戏版本，高于存档版本就可以，不确定存档是哪个版本的话，就把游戏升级到最新版
2. 使用存档转换器，把自己的存档转成自己的存档，但是存档的版本会降级，降到大概刚发售时的版本，这样的话无论如何你的存档都不会高于你的游戏版本

> 假如你有一个1.14版本的游戏本体，你创建一个新存档，那这个存档的版本就是1.14，你游戏升级到1.15了，你启动一次游戏，你的存档就升级成1.15了，这时候你再启动1.14及以下版本的游戏读取这个存档的话就会提示这个

---

# Steam datagram relay error: k_ESteamNetworkingAvailability_Unknown

{: .note-title }
> 大概意思是
>
> 连接不上steam网络

> 常见于正版无缝联机和学习版steam无缝联机玩家，旧版的学习版局域网玩家也会遇到

![steamDB未知.jpg](/assets/images/steamDB未知.jpg)

正常的解决方案就是加速steam，如果解决不了，要么是网络不好（没人给我反馈过这种情况），要么就是别的问题，比如：
1. 用的加速器不行，比如steam++（有概率不行，最好换别的加速），我一般UU，很多加速器加速steam都是免费的
2. 你是学习版，但是没有打联机补丁，直接安装了无缝联机mod，使用道具也会提示这个，学习版怎么无缝联机参考：[安装无缝联机]({{site.baseurl}}/docs/upgrade/esrc/)
3. 你是学习版局域网联机，不建议使用，参考第二条的教程换成学习版steam联机

{: .note-title }
> 怎么分辨我是不是学习版steam无缝联机？
> 
> 如果运行游戏的时候，steam库里面有一个叫`spacewar`的游戏在运行，那就是，否则不是

---

# Steam lobby search timed out

{: .note-title }
> 大概意思是
>
> steam大厅搜索超时

![steamDB超时.png](/assets/images/steamDB超时.png)

正常的解决方案就是加速steam，如果解决不了，要么是网络不好，要么就是别的问题，比如：
1. 用的加速器不行，比如steam++（有概率不行，最好换别的加速），我一般UU，很多加速器加速steam都是免费的

---