---
title: 无缝+光荣商人
nav_order: 2
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

[法魂整合光荣商人(含正版学习版)](https://www.bilibili.com/video/BV1qDqeY4E4X/){:target="_blank"}

# 图文教程

## 下载光荣商人

[光荣商人 N网地址](https://www.nexusmods.com/eldenring/mods/5192){:target="_blank"}


## 光荣商人目录结构说明

```yaml
├─ ermerchant.dll # 光荣商人主逻辑文件
├─ ermerchant.ini # 光荣商人配置文件
└─ LICENSE.txt # 声明文件 可以删
```


## 光荣商人配置文件`ermerchant.ini`说明

```ini
[ermerchant]
; 如果是true，则商人商店里的武器会自动强化到与你拥有的最高强化相同
; 比如 你拥有的最高强化是+10 则商店中所有武器都是+10 （失色强化与普通强化之间会换算）
; 不想要这个效果就改成false
auto_upgrade_weapons = true
```

## 安装光荣商人

把文件拖进游戏目录

![光荣商人游戏根目录.png](/assets/images/光荣商人游戏根目录.png)

### 配置mod引擎配置文件`config_eldenring.toml`

![光荣商人mod引擎配置.png](/assets/images/光荣商人mod引擎配置.png)

因为要兼容无缝，所以既要有无缝的dll文件，又要有光荣商人的dll文件，在无缝那一行尾部加一个英文的逗号，用来分隔两个路径

注意这个配置文件中的标点符号都要是英文的，修改完记得保存

## 大功告成 🎉🎉🎉

> 开始游戏之前使用加速器加速一下steam，如果你不跟人联机，那不用加速

可以双击`modengine2_launcher.exe`启动游戏了

你可能需要：[常见问题]({{site.baseurl}}/docs/common_problem/)

## 游戏内mod使用说明

要使用mod的功能需要到艾蕾教堂找咖列，也就是那个商人，跟他对话就可以看到对话菜单变了

![光荣商人对话菜单.png](/assets/images/光荣商人对话菜单.png)


---

