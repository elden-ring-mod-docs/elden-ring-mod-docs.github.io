---
title: 无缝+法魂
nav_order: 6
parent: (大成)利用mod引擎来整合无缝和其他mod
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

# 视频教程

[法魂mod兼容无缝教程(含正版学习版)-授人以渔](https://www.bilibili.com/video/BV1cLieYtE5d){:target="_blank"}

# 图文教程

## 下载法魂

[法魂 N网地址](https://www.nexusmods.com/eldenring/mods/3419){:target="_blank"}

[简体中文补丁 N网地址](https://www.nexusmods.com/eldenring/mods/3511){:target="_blank"}

夸克网盘：[「法魂2.2.3中文版（游戏版本1.16）.zip」](https://pan.quark.cn/s/708d42e573de){:target="_blank"}

## 法魂mod文件说明

未列出所有文件

```yaml
├─ locale/ # 空文件夹
├─ mod/
│    ├─ action/
│    ├─ asset/ #地图素材模型与贴图
│    ├─ chr/ #人物与NPC的模型与动作数据
│    ├─ event/ #事件数据
│    ├─ logs/ #日志数据
│    ├─ map/ #地图模型及相关文件
│    ├─ menu/ #UI布局以及贴图文件
│    ├─ msg/ #存放多语种的文本信息，如人物对话，物品介绍等
│    │    ├─ engus/ #英文
│    │    ├─ zhocn/ #简体中文
│    │    └─ zhotw/ #繁体中文
│    ├─ param/ #渲染参数和系统参数
│    ├─ parts/ #武器模型和装备模型
│    ├─ script/ #敌人AI代码文件
│    ├─ sd/
│    ├─ sfx/ #特效文件
│    ├─ shader/ #着色器
│    ├─ sound/ #语音、音效、bgm
│    ├─ altsaves.toml
│    ├─ CMI.dll
│    ├─ eldenring_alt_saves.dll
│    ├─ erd_tools.ini # ErdTools.dll的配置文件
│    ├─ ErdTools.dll
│    ├─ erdyes.dll
│    ├─ erdyes.ini # erdyes.dll的配置文件
│    ├─ ertransmogrify.dll
│    ├─ ertransmogrify.ini # ertransmogrify.dll的配置文件
│    ├─ regulation.bin # 规则文件 一般叫它bin文件  游戏的规则版本就跟这个文件有关系
│    ├─ Scripts-Data-Exposer-FS.dll
│    └─ sound.json
├─ modengine2/ # mod引擎相关文件
├─ config_eldenring.toml/ # mod引擎配置文件
├─ modengine2_launcher.exe # mod引擎启动文件
└─ Start_Convergence.bat # 法魂自带的启动脚本
```

可以看到`mod/msg`文件夹下已经有了简体中文的文本文件，但是未必是兼容最新版的，可能更新有有延迟，我们把自己单独下载的简体中文补丁放进去

然后目录结构就变成了这样

```yaml
├─ locale/
├─ mod/
│    ├─ action/
│    ├─ asset/
│    ├─ chr/
│    ├─ event/
│    ├─ logs/
│    ├─ map/
│    ├─ menu/
│    ├─ msg/
│    │    ├─ engus/
│    │    ├─ zhocn/ #刚刚放进去的简体中文补丁
│    │    └─ zhotw/
│    ├─ param/
│    ├─ parts/
│    ├─ script/
│    ├─ sd/
│    ├─ sfx/
│    ├─ shader/
│    ├─ sound/
│    ├─ altsaves.toml
│    ├─ CMI.dll
│    ├─ eldenring_alt_saves.dll
│    ├─ erd_tools.ini
│    ├─ ErdTools.dll
│    ├─ erdyes.dll
│    ├─ erdyes.ini
│    ├─ ertransmogrify.dll
│    ├─ ertransmogrify.ini
│    ├─ regulation.bin
│    ├─ Scripts-Data-Exposer-FS.dll
│    └─ sound.json
├─ modengine2/
├─ config_eldenring.toml/
├─ modengine2_launcher.exe
└─ Start_Convergence.bat
```

可以看到法魂mod文件已经自带一个mod引擎了，所以我们可以直接把这些文件放到游戏目录里

> `locale`文件夹可以删掉

![法魂游戏目录.png](/assets/images/法魂游戏目录.png)

那它还有一些dll文件怎么办呢？我们打开mod引擎的配置文件`config_eldenring.toml`，可以发现它已经帮我们配置好了，包括无缝的dll它也帮我们配置好了

![法魂mod引擎配置.png](/assets/images/法魂mod引擎配置.png)

相关知识点参考：[mod引擎介绍]({{site.baseurl}}/docs/upgrade/ersc_modengine/)


## 大功告成 🎉🎉🎉

> 开始游戏之前使用加速器加速一下steam，如果你不跟人联机，那不用加速
> 这个mod跟人联机的话需要所有人都安装

可以双击`modengine2_launcher.exe`启动游戏了

你可能需要：

[常见问题]({{site.baseurl}}/docs/common_problem/)

[mod引擎闪退解决方案合集](https://www.bilibili.com/video/BV1aNKTeLEaz/){:target="_blank"}

## 效果展示

标题页面可以看到法魂的版本号，以及无缝的版本号（如果你安装了的话），如果跟人联机的话，这四个版本号需要跟队友相同

![法魂标题页面版本号.png](/assets/images/法魂标题页面版本号.png)

## 为什么不用`Start_Convergence.bat`启动

`Start_Convergence.bat`启动适用于正版且steam和游戏本体在同一个盘里，好处是法魂的游戏文件放在哪都能启动，不是必须放到游戏目录，但是不适用于学习版，本教程更偏向于一种通用的流程

`modengine2_launcher.exe`启动适用于mod引擎放在游戏目录了，比如本教程这种，无论学习版还是正版都适用

具体的mod引擎启动原理参考视频：

[学习版再也不用找专用的mod引擎辣，mod引擎通用性教程-附原理讲解](https://www.bilibili.com/video/BV1takGYZE5x/){:target="_blank"}



---

