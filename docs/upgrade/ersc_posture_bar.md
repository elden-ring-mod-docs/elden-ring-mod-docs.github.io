---
title: 无缝+韧性条显示
nav_order: 3
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

# 图文教程

## 下载韧性条显示mod

[韧性条显示mod Github地址](https://github.com/Mordrog/EldenRing-PostureBarMod/releases){:target="_blank"}

[韧性条显示mod N网地址](https://www.nexusmods.com/eldenring/mods/3405){:target="_blank"}

## 韧性条显示mod文件说明

```yaml
├─ PostureBarResources/ # 资源文件夹
├─ PostureBarMod.dll # 主要逻辑代码文件
├─ PostureBarModConfig - SekiroBar.ini # 只狼样式配置文件
└─ PostureBarModConfig.ini # 配置文件
```

其中`PostureBarModConfig - SekiroBar.ini`是只狼样式文件，要使用的话有两种方法，二选一即可
1. 把`PostureBarModConfig - SekiroBar.ini`文件内的内容复制到`PostureBarModConfig.ini`中并保存
2. 将`PostureBarModConfig - SekiroBar.ini`重命名为`PostureBarModConfig.ini`

## 安装韧性条显示mod

将文件复制到游戏目录

![韧性条游戏目录.png](/assets/images/韧性条游戏目录.png)

修改mod引擎的配置文件`config_eldenring.toml`，以让mod引擎加载韧性条的dll文件

![韧性条mod引擎配置.png](/assets/images/韧性条mod引擎配置.png)

因为要兼容无缝，所以既要有无缝的dll文件，又要有韧性条显示mod的dll文件，在无缝那一行尾部加一个英文的逗号，用来分隔两个路径

注意这个配置文件中的标点符号都要是英文的，修改完记得保存

## 大功告成 🎉🎉🎉

> 开始游戏之前使用加速器加速一下steam，如果你不跟人联机，那不用加速
> 这个mod跟人联机的话不要求所有人都安装，也就是可以就你自己装，不影响联机

可以双击`modengine2_launcher.exe`启动游戏了



你可能需要：

[常见问题]({{site.baseurl}}/docs/common_problem/)

[mod引擎闪退解决方案合集](https://www.bilibili.com/video/BV1aNKTeLEaz/){:target="_blank"}


## 效果展示

![韧性条效果.png](/assets/images/韧性条效果.png)


只狼样式：

![韧性条只狼效果.png](/assets/images/韧性条只狼效果.png)


---

