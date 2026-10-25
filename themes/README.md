# 主题

主题是一个文件夹，其中包含一个 `config.json`，还可选地包含一张 `wallpaper.jpg`。推送一个主题后，无需重新构建
APK，就能改变电视上启动器的 dock、布局和外观：启动器会在下次启动时读取 `config.json`，把它作为叠加层
覆盖在内置的 `config.xml` 之上。
在启动器设置中所做的选择会一直优先生效，直到你选择 Follow theme 为止。推送一个主题或
使用 `tools/theme.sh --reset`，也会清除电视上已做的这些列数与动效选择。

```bash
TV_HOST=192.168.1.50 tools/theme.sh themes/aurora          # push a theme and restart Home
TV_HOST=192.168.1.50 tools/theme.sh --reset                # back to the built-in config.xml
powershell -ExecutionPolicy Bypass -File tools\theme.ps1 -TvHost 192.168.1.50 themes\aurora
```

| 主题 | 说明 |
|---|---|
| `default/` | 将内置外观原样写成 JSON，作为自制主题的起点 |
| `aurora/` | 深色极光壁纸（藏青底色上的青绿色与紫色，底部更暗），并配有相称的背景色 |
| `six-columns/` | 每行六个更小的磁贴，dock 下方有一行网格可见 |

## 配置键

每个键都是可选的：缺失的键会沿用 `config.xml` 中的值，未知或类型不对的键会被忽略，
而无法解析的文件会被整体忽略，因此主题绝不会让 Home 出问题。

| 键 | 类型 | 含义 |
|---|---|---|
| `dock_apps` | 包名列表 | dock 一行的应用，按此顺序排列；缺失的应用会被跳过 |
| `hidden_apps` | 包名列表 | 永远不会显示为磁贴 |
| `live_tv_package`, `live_tv_action` | 字符串 | Live TV 应用，以及在没有 leanback 入口时用于启动它的 action |
| `source_panel_service`, `source_panel_action` | 字符串 | 电视自带的信号源面板，用于没有 TvInputManager 的机型 |
| `input_action` | 字符串 | 当没有任何应用处理标准 `VIEW` 时，随 HDMI/AV 行的频道 URI 一起发送的 action（XGIMI：`com.xgimi.action.hdmiPlayer`） |
| `columns` | 1 到 8 | 每行磁贴数量；从 5 起，磁贴会缩小以适应屏幕 |
| `rows_below_dock` | 0 到 3 | dock 下方保留可见的网格行数 |
| `shamsi_date` | 布尔值 | 在公历日期上方显示 Solar Hijri 日期 |
| `module_cards` | 布尔值 | 查找模块卡片并就其进行询问（`true`）；设为 `false` 会关闭该功能 |
| `reduced_motion` | 布尔值 | 为性能较弱的 GPU 提供更平缓的动效：高亮弹簧更硬、磁贴不过冲、淡入淡出更短、不回放入场动画 |
| `vpn_app` | 字符串 | 配置了 VPN 时，点击网络胶囊按钮会打开的应用；当没有 VPN 连接时，还会显示红色的 "VPN off" 徽标 |
| `animations` | 布尔值 | 基础的焦点、玻璃、标题与磁贴入场动效；默认为 true |
| `advanced_effects` | 布尔值 | 可选的磁贴浮起、图标缩放、平滑环境色与应用打开特效；默认为 false |
| `show_home_settings_shortcut` | 布尔值 | 当电视带桌面选择器时，保持可选的 Default-home 磁贴可见；默认为 false |
| `background_color` | `#RRGGBB` | 所有内容背后的背景色；默认为黑色 |
| `sky_intensity` | 0 到 100 | 昼夜背景：跟随时刻变化的深色渐变，0 表示隐藏（默认） |
| `wallpaper` | 布尔值 | 显示主题文件夹中的 `wallpaper.jpg`（`true`），或忽略它（`false`） |

## 壁纸

`wallpaper.jpg` 会全屏绘制在启动器背后，居中裁剪。请让它保持偏暗、1920×1080，大小约在 300 KB 以内：
文字、hero 名称和 dock 色带都是针对黑色背景设计的，而且 1 GB 内存的电视在每次回到 Home 时
都要把图片解码到内存中。大于屏幕尺寸的图片会被降采样。

## 减弱动效

`"reduced_motion": true` 保持外观不变，但让动效更加平缓：高亮弹簧变得生硬而不再弹跳，磁贴缩放不再过冲，
淡入淡出更短，而且当你回到 Home 时，不再回放磁贴的入场动画。请把它用在 GPU 跟不上的电视上；
已知的一例是运行 Android 10 的 MediaTek MT5895。
默认值 `false` 则保持正常动效。

```json
{ "reduced_motion": true }
```

## 昼夜背景

`"sky_intensity": 60` 会在壁纸之上、所有其他内容之下绘制一层跟随时刻变化的深色渐变：夜晚是深蓝，
白天是柔和的浅蓝，随后是暖色的地平线，在晚上八点前不久达到峰值。
底边附近的光晕会随太阳从左向右移动。颜色始终保持深色，因此白色时钟、hero 名称和 dock 色带
仍能保持对比度。它以一张 480×270 位图的形式绘制，每分钟重绘一次，从不做动画，因此
即使是 1 GB 内存的电视也毫无压力。`0` 表示保持纯色背景；
默认关闭（reference launcher 的外观与之前完全一致）。

```json
{ "sky_intensity": 60 }
```

## 添加主题

在这里开一个 PR，附上一个新的主题文件夹、上面表格中新增的一行说明，并在 PR 描述中放一张真实电视上的截图。
除非主题是为某台特定电视制作的，否则请让 dock 列表保持通用（即那些主流流媒体应用），
并说明你在哪台电视上测试过。
