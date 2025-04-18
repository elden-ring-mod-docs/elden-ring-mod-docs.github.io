---
title: (初阶)安装无缝
nav_order: 2
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

# 视频教程

- 正版：[无缝联机兼容DLC版本使用教程](https://www.bilibili.com/video/BV1si421e7bM/){:target="_blank"}
- 学习版：[学习版steam无缝联机教程兼容DLC](https://www.bilibili.com/video/BV1Ni421v71g/){:target="_blank"}

---

# 图文教程

## 下载最新版无缝联机mod

- [无缝联机mod N网地址](https://www.nexusmods.com/eldenring/mods/510){:target="_blank"}
- [无缝联机mod Github地址](https://github.com/LukeYui/EldenRingSeamlessCoopRelease/releases){:target="_blank"}

N网地址会有mod详细介绍及说明，看不懂英文的话可以翻译着看

## 无缝联机mod目录结构说明

```yaml
├─ ersc_launcher.exe #无缝自带启动器
└─ SeamlessCoop/
    ├─ ersc.dll #无缝的代码逻辑核心文件
    ├─ ersc_settings.ini #无缝的配置文件
    ├─ crashpad/
    │    └─ crashpad_handler.exe #无缝崩溃时dump内存的
    └─ locale/ #这个文件夹内是各国语言翻译
         ├─ arabic.json
         ├─ brazilian.json
         ├─ dutch.json
         ├─ english.json #英文
         ├─ finnish.json
         ├─ french.json
         ├─ german.json
         ├─ hungarian.json
         ├─ italian.json
         ├─ japanese.json
         ├─ koreana.json
         ├─ latam.json
         ├─ polish.json
         ├─ russian.json
         ├─ schinese.json #简体中文
         ├─ spanish.json
         ├─ tchinese.json #繁体中文
         ├─ thai.json
         └─ vietnamese.json
```


## 安装无缝联机mod

拖进游戏目录即可，注意文件夹层级结构如下图

![无缝拖进游戏目录.png](/assets/images/无缝拖进游戏目录.png)


## 无缝联机mod配置文件`SeamlessCoop/ersc_settings.ini`说明

可根据自己喜好自行修改，关于缩放的部分请谨慎修改，可能会影响游戏体验

{: .note }
密码`cooppassword`和语言`mod_language_override`是默认为空的，下方为了举例才填写了一个案例

```ini
[GAMEPLAY]
; 是否允许被入侵，1允许 0不允许 不想被入侵就改成0
allow_invaders = 1
; 是否有死亡惩罚，1有 0没有，死亡惩罚就是每次死亡后背包里会多一个腐败精华，一共有5种 每种的debuff都不一样，坐火消除
death_debuffs = 1
; 多人游戏时是否允许召唤骨灰，1允许 0不允许
allow_summons = 1
; 队友头顶显示的信息 0显示“勾指主人” 1什么也不显示 2显示延迟 3显示人物等级 4显示死亡次数 5显示人物等级和延迟
overhead_player_display = 2
; 是否跳过启动游戏后的开屏动画（徽标logo），1跳过 0不跳过
skip_splash_screens = 1
; 加载存档前的游戏音量 0静音 10最大音量 这个保持5就好，针对启动游戏后 按任意键之前 这个时间区间内的游戏音量过大的问题
default_boot_master_volume = 5
[SCALING]
; 敌人的生命值缩放（%）（默认值：每增加一位玩家会使敌方生命值增加35%）
enemy_health_scaling = 35
; 敌人的伤害值缩放（%） （默认值：每增加一位玩家会使敌方伤害增加0%）
enemy_damage_scaling = 0
; 敌人的韧性值缩放（%）（默认值：每增加一位玩家会使敌方韧性增加15%）
enemy_posture_scaling = 15
; boss的生命值缩放（%）（默认值：每增加一位玩家会使boss生命值增加100%）
boss_health_scaling = 100
; boss的伤害值缩放（%） （默认值：每增加一位玩家会使boss伤害增加0%）
boss_damage_scaling = 0
; boss的韧性值缩放（%）（默认值：每增加一位玩家会使boss韧性增加20%）
boss_posture_scaling = 20
[PASSWORD]
; 房间密码(会话密码) 默认是空的，必须填写才能进入游戏，注意等于号后面有个空格（大家都默认的），就算密码一样，有空格和没空格也会加入不到一起
cooppassword = 123456
[SAVE]
; 存档的扩展名 (原版游戏的扩展名是.sl2). 可以使用任何字母数字字符，最大长度120
save_file_extension = co2
[LANGUAGE]
; mod的语言，留空的话就是你启动游戏时游戏的语言，如果想强制简体中文的话就填schinese，但前提是你locale文件夹内有对应的schinese.json文件，其他语言也是一样
mod_language_override = schinese
```

{: .warning }
必须填写密码才能正常进入游戏，否则会有错误提示

{: .warning }
修改配置文件后记得保存，且重启游戏才能生效(如果在开着游戏的情况下修改的话)

## 如果你是学习版，需要额外打一个联机补丁

如果你想变成学习版，和学习版的小伙伴一起联机，也需要打上这个补丁**变成学习版**
> 如果你有正版的话，建议复制出来一份再打这个补丁，这样的话正版和学习版是分开的，想玩哪个版本就找对应的目录启动就好了


夸克网盘：[「EldenRing_Fix_Repair_Steam_Generic.zip」](https://pan.quark.cn/s/875d7d21db25){:target="_blank"}

百度网盘：[EldenRing_Fix_Repair_Steam_Generic.zip](https://pan.baidu.com/s/1mtWwaLfpjhVIhBy5NQUDMA?pwd=my8q){:target="_blank"}

![老头环学习版steam联机补丁.png](/assets/images/老头环学习版steam联机补丁.png)

拖到游戏目录里

![学习版steam联机游戏目录.png](/assets/images/学习版steam联机游戏目录.png)


# 大功告成 🎉🎉🎉

> 开始游戏之前使用加速器加速一下steam，如果你不跟人联机，那不用加速

可以双击`ersc_launcher.exe`启动游戏了

你可能需要：[常见问题]({{site.baseurl}}/docs/common_problem/)

# 如何确定我是不是安装成功了

启动游戏之后，标题页面右下角如果显示无缝联机mod的版本号，就是安装成功了

![标题页面无缝版本号.png](/assets/images/标题页面无缝版本号.png)

# mod道具说明

进入游戏后**坐火**可以获得mod道具

![袖珍大壶.png](/assets/images/袖珍大壶.png) 开启房间的道具，房主使用

![玛丽卡雕像.png](/assets/images/玛丽卡雕像.png) 加入房间的道具，非房主玩家使用

![挑战者之针.png](/assets/images/挑战者之针.png) 入侵道具，入侵别的无缝联机玩家

![离别迷雾.png](/assets/images/离别迷雾.png) 房主使用的话是关闭房间，非房主玩家使用的话是离开房间

![判官法典.png](/assets/images/判官法典.png) 修改玩家之前的规则的道具，可以开友伤来PVP，也可以分队伍PVP

![卢恩之酒.png](/assets/images/卢恩之酒.png) 花费卢恩获得和卢恩弯弧一样的效果，也就是激活大卢恩

![干缩手指.png](/assets/images/干缩手指.png) 吸引更多的入侵者入侵你
