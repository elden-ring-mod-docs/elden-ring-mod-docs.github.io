---
title: 无缝+哥布林
nav_order: 4
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

[无缝兼容哥布林mod教程](https://www.bilibili.com/video/BV1eiNhe7EZr){:target="_blank"}

# 图文教程

## 下载哥布林mod及汉化补丁

[哥布林mod N网地址](https://www.nexusmods.com/eldenring/mods/3091){:target="_blank"}

[简体中文补丁 N网地址](https://www.nexusmods.com/eldenring/mods/6235){:target="_blank"}

## 哥布林mod文件说明

```yaml
├─ menu/ # UI布局以及贴图文件
├─ msg/ # 存放多语种的文本信息，如人物对话，物品介绍等
│    └─ engus/ # 英文
├─ script/ # 一般是敌人AI代码文件 这里应该是修改了部分对话选项 游戏内体现为篝火选项的变化
├─ Readme.txt # 说明文件 里面全是英文 可以翻译一下看下 这个文件可以删
└─ regulation.bin # 规则文件 一般叫它bin文件  游戏的规则版本就跟这个文件有关系
```

可以看到`msg`文件夹下只有英文的文本文件，我们把简体中文的文本文件放进去

然后目录结构就变成了这样

```yaml
├─ menu/
├─ msg/
│    ├─ engus/
│    └─ zhocn/ # 简体中文
├─ script/
├─ Readme.txt
└─ regulation.bin
```

可以看出mod文件目录类似游戏解包目录结构，所以这个文件直接放到mod引擎的mod文件夹里

相关知识点参考：[mod引擎介绍]({{site.baseurl}}/docs/upgrade/ersc_modengine/)

![哥布林mod引擎目录.png](/assets/images/哥布林mod引擎目录.png)


## 大功告成 🎉🎉🎉

> 开始游戏之前使用加速器加速一下steam，如果你不跟人联机，那不用加速
> 这个mod跟人联机的话不要求所有人都安装，也就是可以就你自己装，不影响联机

可以双击`modengine2_launcher.exe`启动游戏了

你可能需要：[常见问题]({{site.baseurl}}/docs/common_problem/)


## 地图上没有任何变化?

这个mod在某个版本之后**默认地图上什么都不显示**，需要到篝火处，有个`配置哥布林地图`选项

![哥布林mod菜单.png](/assets/images/哥布林mod菜单.png)

这个目录是可以上下滑动的，可以调整在地图上显示和隐藏哪些图标


# 注意事项

这个mod的图标位置是确定的，所以无法与其他内容修改mod兼容，比如法魂


---

