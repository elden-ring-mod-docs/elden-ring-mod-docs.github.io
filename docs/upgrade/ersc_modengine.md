---
title: (高阶)安装mod引擎来启动无缝
nav_order: 3
parent: 萌新进阶之路
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
# 前言

## 为什么要安装mod引擎

mod引擎的作用是启动游戏时加载mod文件，并且如果mod文件没有冲突的话可以同时加载多个mod，所以我们可以利用这个特性来整合无缝联机mod和其他mod

## mod引擎加载mod的原理浅谈

如果是dll文件，那就是dll注入，原理就是在游戏启动时，把dll文件加载到游戏进程的内存中，通过hook游戏原有的函数来实现自己的逻辑（最热门的就是无缝联机）

那如果是对游戏内原有资产的修改，比如修改某个战技的动作，修改武器的伤害，修改地图布局，修改环境模型，修改特效，修改怪物分布，这种数据肯定是在游戏某个文件内保存着呢，我想修改的话就是找到这个文件，然后修改成我想要的样子。

但是游戏目录里就这么几个文件，没看到这些数据放在哪了，其实就在那几个`.bdt`大文件里，可以理解为压缩了，变成了几个压缩包，然后游戏运行的时候再取出来

想解压的话可以使用N网的解包工具[UXM Selective Unpacker N网地址](https://www.nexusmods.com/eldenring/mods/1651){:target="_blank"}

原版游戏解包之后的文件夹结构如下：（未列出所有文件）
```yaml
├─ action/
├─ asset/ #地图素材模型与贴图
│    ├─ aet/ #贴图文件
│    └─ aeg/ #模型文件
├─ chr/ #人物与NPC的模型与动作数据
├─ cutscene/ #过场动画文件
├─ event/ #事件数据
├─ expression/ #记录文件
├─ facegen/ #捏脸数据（基础脸型
├─ font/ #字体
├─ map/ #地图模型及相关文件
├─ menu/ #UI布局以及贴图文件
├─ msg/ #存放多语种的文本信息，如人物对话，物品介绍等
│    ├─ engus/ #英文
│    ├─ zhocn/ #简体中文
│    └─ zhotw/ #繁体中文
├─ param/ #渲染参数和系统参数
├─ parts/ #武器模型和装备模型
├─ script/ #敌人AI代码文件
├─ sfx/ #特效文件
├─ shader/ #着色器
└─ sound/ #语音、音效、bgm
```

我们以法魂这个mod的目录结构举例：

![法魂目录结构.png](/assets/images/法魂目录结构.png)

可以看到高亮的这几个目录是跟游戏解包后的目录结构重合的，也就是说，这些对游戏原有资产的修改的mod，本质就是文件替换，也就是游戏运行的时候要加载对应的文件了，让游戏优先加载你mod目录下的同名文件，那就做到了修改游戏的效果，mod引擎从中起到的作用就是让游戏优先加载你的文件

在了解原理后，我们在使用mod引擎的时候就会更加得心应手
> 怎么修改这些文件属于**制作mod**的范畴，本教程不会涉及

# 视频教程

[无缝联机兼容mod引擎教程(含正版和学习版)](https://www.bilibili.com/video/BV13J4m1M7Eu){:target="_blank"}

# 图文教程

## 下载mod引擎

[mod引擎 Github地址](https://github.com/soulsmods/ModEngine2/releases){:target="_blank"}

夸克网盘：[「ModEngine-2.1.0.0-win64.zip」](https://pan.quark.cn/s/f2a98dd85fbd){:target="_blank"}

百度网盘：[ModEngine-2.1.0.0-win64.zip](https://pan.baidu.com/s/1kopbV7a4p6ayv-f0KXUcOw?pwd=fxt6){:target="_blank"}

## mod引擎的目录结构说明

![mod引擎目录结构.png](/assets/images/mod引擎目录结构.png)

```yaml
├─ mod/ #默认给玩家放mod文件的地方
├─ modengine2/ #mod引擎的逻辑代码
├─ config_armoredcore6.toml #机甲核心6的mod引擎配置文件
├─ config_darksouls3.toml #动黑暗之魂3的mod引擎配置文件
├─ config_eldenring.toml #艾尔登法环的mod引擎配置文件
├─ launchmod_armoredcore6.bat #启动机甲核心6的mod引擎bat脚本
├─ launchmod_darksouls3.bat #启动黑暗之魂3的mod引擎bat脚本
├─ launchmod_eldenring.bat #启动艾尔登法环的mod引擎bat脚本
├─ modengine2_launcher.exe #mod引擎的启动程序，不要给这个文件重命名
└─ README.txt #说明文件，可以删
```

因为我们要启动的是艾尔登法环，所以其他游戏的相关文件都可以删

```yaml
├─ mod/ #默认给玩家放mod文件的地方
├─ modengine2/ #mod引擎的逻辑代码
├─ config_eldenring.toml #艾尔登法环的mod引擎配置文件
├─ launchmod_eldenring.bat #启动艾尔登法环的mod引擎bat脚本
└─ modengine2_launcher.exe #mod引擎的启动程序，不要给这个文件重命名
```

我们只保留这些就可以了，拖进游戏目录

![mod引擎游戏目录.png](/assets/images/mod引擎游戏目录.png)

## mod引擎配置文件`config_eldenring.toml`说明

```toml
[modengine]
# 是否开启调试，如果设置为true的话小黑窗会打印更多的信息
debug = false
# 配置dll文件路径的地方，用来加载dll文件，示例：
# external_dlls = [ "coolmod.dll", "D:\\nicemods\\nicemod.dll", "sosofolder\sosomod.dll" ]
external_dlls = []
[extension.mod_loader]
# 是否加载mod，改成false的话不会加载下方mods配置项对应的目录下的文件，只会加载dll文件
enabled = true
# Not currently supported for Elden Ring
loose_params = false
# 可以配置多个存放mod文件的目录配置，并命名不同的名字，比如：
# mods = [
#    { enabled = true, name = "coolmod", path = "mod1" },
#    { enabled = true, name = "nicemod", path = "mod2" },
#    { enabled = true, name = "sosomod", path = "mod3" }
# ]
mods = [
    { enabled = true, name = "default", path = "mod" }
]
# 用来调试游戏的，给逆向游戏的开发者用的
[extension.scylla_hide]
enabled = false
```

## 让mod引擎加载无缝联机mod

打开mod引擎的配置文件`config_eldenring.toml`，并配置`external_dlls`配置项

![mod引擎配置文件加载无缝.png](/assets/images/mod引擎配置文件加载无缝.png)

> 我这里用的是第三方的文本编辑器，会有语法高亮 [下载地址](https://rizonesoft.com/downloads/notepad3/){:target="_blank"}

{: .highlight }
一定要是英文符号，修改完记得保存

这里用的是相对路径，相对于谁呢？相对于游戏目录里的`modengine2_launcher.exe`，当然你也可以填绝对路径，看你喜欢

## 大功告成 🎉🎉🎉

> 开始游戏之前使用加速器加速一下steam，如果你不跟人联机，那不用加速

可以双击`modengine2_launcher.exe`启动游戏了

你可能需要：[常见问题]({{site.baseurl}}/docs/common_problem/)