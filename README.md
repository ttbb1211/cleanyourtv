<p align="center">
  <a href="https://cleanyour.tv"><img src="https://raw.githubusercontent.com/Gathin23/cleanyourtv/main/docs/banner.png" alt="CleanYourTV. Your TV, minus the ads." width="800"></a>
</p>

<p align="center">
  <a href="https://cleanyour.tv">cleanyour.tv</a> ·
  <a href="PROMPT.md">Prompt 原文</a> ·
  <a href="examples/">66 份电视清单</a> ·
  <a href="SHOWCASE.md">15 个基于它的项目</a> ·
  <a href="https://x.com/gathint/status/2111379569030939102">那条推文</a>
</p>

<p align="center">
  <a href="https://github.com/Gathin23/cleanyourtv/stargazers"><img src="https://img.shields.io/github/stars/Gathin23/cleanyourtv?style=flat&cacheSeconds=1800&color=cfffcf&labelColor=15181e" alt="Stars"></a>
  <a href="https://github.com/Gathin23/cleanyourtv/pulls?q=is%3Amerged"><img src="https://img.shields.io/github/issues-pr-closed/Gathin23/cleanyourtv?style=flat&cacheSeconds=1800&label=merged%20PRs&color=cfffcf&labelColor=15181e" alt="Merged PRs"></a>
  <a href="https://github.com/Gathin23/cleanyourtv/network/members"><img src="https://img.shields.io/github/forks/Gathin23/cleanyourtv?style=flat&cacheSeconds=1800&color=cfffcf&labelColor=15181e" alt="Forks"></a>
  <a href="https://github.com/Gathin23/cleanyourtv/graphs/contributors"><img src="https://img.shields.io/github/contributors/Gathin23/cleanyourtv?style=flat&cacheSeconds=1800&color=cfffcf&labelColor=15181e" alt="Contributors"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/licence-MIT-cfffcf?style=flat&labelColor=15181e" alt="MIT"></a>
  <a href="https://buymeacoffee.com/gathint"><img src="https://img.shields.io/badge/support-%E2%9D%A4-ff5e8a?style=flat&labelColor=15181e" alt="Support, buy me a coffee"></a>
</p>

通过 Wi-Fi 清除任意 Android TV 或 Google TV 上的预装垃圾软件（bloatware），把塞满广告的主屏幕换成一个外观神似 Apple TV 的清爽 launcher。**无需 root，无需数据线，不卸载任何东西，反悔时一条命令即可恢复。**

<h3 align="center">已实测 66 台电视 &nbsp;·&nbsp; 25 个品牌 &nbsp;·&nbsp; 14 种语言 &nbsp;·&nbsp; 300 KB 的 launcher</h3>

![Before: stock Google TV home with a sponsored ad. After: the Clean Your TV launcher](docs/stock-vs-new-side.jpg)

> 今天下午给我爸妈的电视来了波 vibe coding！以前连 Netflix 都还没进去，就先看到一条赞助广告。把型号发给 Claude Code，它自己在 Wi-Fi 上找到电视，移除了 25 个小米系统包，还写了个新 launcher。现在看着就像 Apple TV，哈哈。
>
> [@gathint，2026 年 10 月 17 日](https://x.com/gathint/status/2111379569030939102)。这里的大多数电视清单都来自那条推文的回复区。本仓库在 19 日之前叫 tv-vibehack，旧链接仍然有效。

## 工作原理

Android TV 和 Android 手机用的是同一套调试桥（ADB）。在电视的开发者选项里打开 USB 调试，对你的电脑授权一次，剩下的就是标准的 Android 工具流程：

1. **备份**已安装包的列表和系统设置。
2. 用 `pm disable-user` **停用**厂商的遥测、广告服务、内容推荐行和预装垃圾应用。什么都不会被卸载，因此恢复脚本可以撤销每一步。
3. **安装**一个小巧的原生 launcher，并将其设为默认主屏幕。

预装垃圾因品牌而异，所以 prompt 会让你的编程助手在你的电视上自行探测，并在动任何你可能用得到的东西之前先询问你。

## 快速开始

你需要一台与电视连在同一个 Wi-Fi 下的电脑，以及一个可以执行 shell 命令的编程助手（Claude Code 或同类工具）。

| | |
|---|---|
| **1. 在电视上** | 设置 → 设备偏好设置 → 关于 → 在 **Build** 一项上连按 OK 键七次 → 返回 → 开发者选项 → 打开 **USB 调试**。如果看到"网络调试"或"ADB 调试"开关，也一并打开。让电视保持开机。 |
| **2. 在你的电脑上** | 把 [`PROMPT.md`](PROMPT.md) 粘贴给你的助手，并填入你的电视型号。 |
| **3. 跟着提示走** | 在电视上确认"允许 USB 调试？"，然后回答核对清单：你常用哪些应用、dock 里放哪四个、是否保留语音助手、Chromecast 和系统更新。 |

助手会完成备份、debloat、构建并安装 launcher，并用从电视上抓取的截图核对每一步。以本仓库作为上下文，全程约十五分钟。

## 你将获得

- **纯黑的主屏幕**：一条圆角横条 dock 里放着你最爱的四个应用，位置与 Apple TV 如出一辙。
- **top shelf** 以大号字体标出当前聚焦的应用，并伴有一圈取自其海报配色的环境光晕。
- **其余应用收在网格里**，按下"下"键时向上滑出。
- **一枚悬浮的玻璃高光**，在磁贴之间轻盈跃动。聚焦的磁贴会微微抬起并亮出名称。
- **三枚磨砂按钮**：Inputs（HDMI 端口、AV、Live TV）、带网络名称的 Wi-Fi 或有线网络、Settings。
- **[Outfit](https://fonts.google.com/specimen/Outfit) 字体的问候语、纤细时钟与日期**，以及配套的 Clock 屏保。
- **主题**无需重新构建即可更换配色、壁纸、dock 与列数；**模块卡片**让其他应用也能插入一块磁贴——前提是你点头。

以及一台不再处处与你作对的电视：没有赞助推荐行，没有"发现"页的轮番轰炸，没有偷偷回传的数据分析，也没有你从未主动要过的预装应用。

| | |
|---|---|
| ![The top shelf names the focused app over an ambient glow in its colour](docs/focus-2-up-netflix.png) | ![The Inputs popup: HDMI ports with what is connected, AV and Live TV](docs/inputs-menu.jpg) |
| *top shelf 与环境光晕* | *Inputs：HDMI（含连接状态）、AV、Live TV* |
| ![The grid with the glass highlight on a tile and its name beneath](docs/focus-1-fancode.png) | ![The Clock screensaver: a thin clock drifting over the glow](docs/clock-screensaver.png) |
| *应用网格、一枚玻璃高光、磁贴的名称* | *Clock 屏保，缓慢漂移以防烧屏* |
| ![The aurora theme: a wallpaper and tinted pills, pushed without a rebuild](docs/theme-aurora.jpg) | ![Six columns and a six-app dock from a theme's config.json](docs/theme-six-columns.jpg) |
| *Aurora 主题，用 `tools/theme.sh` 推送* | *六列布局与六应用 dock，同一个 launcher* |

## 支持的电视

任何运行 **Android TV** 或 **Google TV** 的设备。三星（Tizen）和 LG（webOS）用的是另一套系统；webOS 移植版见 [SHOWCASE.md](SHOWCASE.md)。**Fire TV** 只适用于 debloat 那一半，因为 Fire OS 不会把主屏幕交给第三方 launcher。少数面向中国市场的 TCL 电视则完全拒绝安装任何 launcher，它们的清单会在开头注明这一点。

贡献者实测过的清单，每个型号一个文件夹，放在 [`examples/`](examples/)：

**TCL** 14 · **Xiaomi** 14 · **Sony** 9 · **Philips** 4 · **Hisense** 3 · **CHiQ** 2 · **Skyworth** 2 ·
AiPro2K · Amazon Fire TV Stick · BenQ · Chromecast with Google TV · Hitachi · Insignia Fire TV ·
NVIDIA Shield · OnePlus · Panasonic · PRISM+ · RCA · Redmi · SANYO · Thomson · Toshiba Fire TV · Vu ·
Stellamore 和 XGIMI 投影仪

<details>
<summary><strong>完整清单</strong></summary>

| 电视 | 系统 |
|---|---|
| AiPro2K (Expressluck, dongnae; Changhong AI PONT 系列) | Android TV 14 |
| Amazon Fire TV Stick 4K, 2018 年第 1 代 (AFTMM, mantis) | Fire OS 6.7.1.1 / Android 7.1 |
| BenQ E55-735 (Changhong AI PONT, DVB96BQ) | Google TV 14 |
| CHiQ AI PONT (Changhong GTVU65, dangni, MediaTek mt5867) | Google TV 14 |
| CHiQ AI PONT (DVB93CQ) | Android TV 11 |
| Chromecast with Google TV 4K (sabrina) | Google TV 14 |
| Hisense HiSmartTV A4 (xiaoyushan, MStar m7322), 印度 | Android TV 9 |
| Hisense SmartTV 4K FFM (huangshan, MediaTek) | Android TV 10 |
| Hisense U75 (hengshan, MediaTek), 拉丁美洲 | Google TV 12 |
| Hitachi 65QLEDSM20 (MTC, bangbae, MediaTek m7322), 澳大利亚 | Android TV 11 |
| Insignia 55" F30 4K Fire TV (NS-55F301NA25, AFTDCT31, duckie) | Fire OS 7 / Android 9 |
| NVIDIA SHIELD TV Pro 2019 (P2897, mdarcy) | Android TV 11 |
| OnePlus TV (D00, 迪拜) | Google TV 14 |
| Panasonic 4KTV-JUP (Jupiter_PA, MediaTek) | Android TV 11 |
| Philips 50PUS8517/12 (TP Vision, PH1M_EA_9970A, MediaTek MT5895), 欧洲 | Android TV 11 |
| Philips 55PUS7503/12 (TP Vision TPM171E, PH7M_EU_5596, MediaTek MT5891), 欧洲 | Android TV 8.0 |
| Philips R8G Google TV (MOKA, whitefield, Realtek RTD2851F), 美国 | Google TV 14 |
| Philips Smart 4K TV (Skyworth, eleonas, MediaTek), 印度 | Google TV 14 |
| PRISM+ Q65 Ultra 2026 QLED 4K AI Google TV (R10G, PRISMPLUS_FFM, MOKA, Realtek RTD2875 SoC, RTD6748 platform) | Google TV 14 |
| RCA AI PONT SA (Changhong, redwood, ISDB92RC; 也以 realme 40 英寸机型销售) | Android 14 |
| Redmi TV (MiTV-ANTL0, starwars) | Android 5.1.1 (并非 Android TV) |
| SANYO ATV R2 (SCBC, Realtek RTD285O) | Android TV 9 |
| Skyworth SWTV-21AE (sunnyvale, MediaTek) | Android TV 14 |
| Skyworth SWTV-24NA-4K NF (eleonas, MediaTek mt5896), 美国 | Google TV 14 |
| Sony BRAVIA 4K AE2 (BRAVIA_AE2, MediaTek MT5897), 北美 | Google TV 14 |
| Sony BRAVIA 4K GB (BRAVIA_ATV2_EU, BRAVIA_ATV2) | Android TV 9 |
| Sony BRAVIA 4K UR2 (BRAVIA_UR2_4K, MediaTek) | Android TV 10 |
| Sony BRAVIA 4K VH2 (KD-55X80J, BRAVIA_VH2, MediaTek), 欧洲 | Google TV 12 |
| Sony BRAVIA 9 II (K-65XR90M2, BRAVIA_AE3, MediaTek MT5838) | Google TV 14 |
| Sony BRAVIA BF1 (BRAVIA 2 II 级别, BRAVIA_BF1_4K_A, MediaTek) | Google TV 12 |
| Sony BRAVIA KD-55X85J (2021, BRAVIA_VH2, MediaTek MT5895), 南美 | Google TV 12 |
| Sony BRAVIA KD-65X80J (2021, BRAVIA_VH2, MediaTek), 印度 | Google TV 10 |
| Sony BRAVIA XBR-65X900E (2017, BRAVIA_ATV2) | Android TV 9 |
| Stellamore T950S 投影仪 (Droidlogic be30a3, Amlogic txhd2) | Android 13 |
| TCL 40S5400A (C06, C06_2K_GB, MediaTek MT9221, 1 GB) | Android TV 11 |
| TCL 43C645 (Smart TV Pro, Realtek RTD2851 / R51MT05, V8-R51MT05-LF1V652) | Android TV 11 上的 Google TV launcher |
| TCL 50EP680 (欧洲, BeyondTV, Realtek rtd285o) | Android TV 11 |
| TCL 55" 4K Google TV, 2023 (G10, G10_4K_US_NF); 另有 TCL 55P6K, 西班牙 (G10_4K_GB_NF_32BIT) | Google TV 12 |
| TCL 55Q10G Pro (中国, tcl_mt5879_cn, MediaTek MT9952) | Android TV 11 |
| TCL 65C725 (Smart TV Pro, BeyondTV4) | Android TV 11 |
| TCL 65C735 (Smart TV Pro, G05, MediaTek), 法国 | Google TV 11 |
| TCL ak30a5 (中国, Amlogic) | Android TV 9 |
| TCL BeyondTV (印度) | Android TV 9 |
| TCL BeyondTV, 欧洲/北欧 (Realtek RTD2851, V8-R851T02-LF1V606) | Android TV 9 |
| TCL BeyondTV2 (拉丁美洲/巴西, Realtek RTD2851) | Android TV 9 |
| TCL QM6K Pro, 2025 (G08, MediaTek tcl9618) | Google TV 14 |
| TCL Smart TV Pro (G05, G05_4K_US, MediaTek MT5889) | Google TV 11 |
| TCL UnionTV, 拉丁美洲 (TCL 制造, 同 Thomson 32HE5800, Realtek RT2841) | Android TV 9 |
| Thomson 32HE5800 (TCL 制造的 UnionTV, Realtek RT2841), 西班牙 | Android TV 9 |
| Toshiba Fire TV (AFTHA004, hazel) | Fire OS 7 / Android 9 |
| Vu 4K (HVCL, lushan, MediaTek), 印度 | Google TV 12 |
| XGIMI Horizon S Pro 投影仪 (XK03H, xgimigalileo, MediaTek) | Android TV 11 |
| Xiaomi Mi Box S (MIBOX4, oneday), 流媒体盒子 | Android TV 9 |
| Xiaomi Mi Box S 第 2 代 (MiTV-AFKR0, jaws), 流媒体盒子 | Google TV 11 |
| Xiaomi Mi TV (MiTV-MOOQ0, croods) | Android TV 10 |
| Xiaomi Mi TV 4A (MiTV-MOOQ1) | Android TV 10 |
| Xiaomi MiTV-AESP0 stick (aquaman, 1 GB) | Android TV 9 |
| Xiaomi MiTV-ASTP1 (maverick), 中国固件 2.40.641.0514.cn, 1 GB RAM, 720p | Android TV 9 (CN 版) |
| Xiaomi MiTV-AXFR1 (rango, Amlogic, 1 GB), 印度 | Android TV 11 |
| Xiaomi MiTV-AXSO0 (dangal; Mi TV 4C Pro 2019 / 4A Pro) | Android TV 9 |
| Xiaomi MiTV-MOOR2 (venom, MediaTek) | Google TV 11 |
| Xiaomi MiTV-MOSR4 (irobot, MediaTek) | Google TV 11 |
| Xiaomi MiTV-MSSP3 (machuca, MediaTek) | Android TV 11 |
| Xiaomi MiTV-MSSP3 (machuca, MediaTek), Android 9 固件 PI.7524 | Android TV 9 |
| Xiaomi TV A Pro 75" 2026 (MiTV-MZTU0, river, MediaTek) | Google TV 14 |
| Xiaomi TV Box S 第 3 代 (MiTV-AFMU0, twilight, Amlogic), 流媒体盒子 | Google TV 14 |

</details>

你的电视不在这里？prompt 会自行探测预装垃圾。之后把你的清单提交上来，下一个用同型号的人就能跳过这一步：[CONTRIBUTING.md](CONTRIBUTING.md)。

## 手动操作

助手能做的每一件事，你都可以亲手执行。这些工具只需要 Python 3，再无其他依赖。

```bash
python3 -m venv tools/venv && tools/venv/bin/pip install -r tools/requirements.txt
export TV_HOST=192.168.1.50                                   # your TV's IP address

tools/venv/bin/python -I tools/tv.py --probe                 # model, Android version, firmware
tools/venv/bin/python -I tools/tv.py 'pm list packages'      # one shell command on the TV
tools/disable.sh examples/xiaomi-mi-tv-4a/debloat.txt        # apply a debloat list
tools/restore.sh examples/xiaomi-mi-tv-4a/debloat.txt        # undo it, stock launcher back
TV_HOST=192.168.1.50 launcher/build-and-install.sh           # build the launcher and make it Home
tools/theme.sh themes/aurora                                 # push a theme; --reset removes it
```

| 工具 | 作用 |
|---|---|
| [`tools/tv.py`](tools/tv.py) | 纯 Python 的 ADB 客户端：shell、批量执行、push、pull。在系统自带 `adb` 二进制被禁用的环境下也能用。 |
| [`tools/b64push.py`](tools/b64push.py) | 以 base64 分块上传 APK 等大文件，并进行校验和验证。 |
| [`tools/disable.sh`](tools/disable.sh), [`restore.sh`](tools/restore.sh) | 应用或撤销一份 debloat 清单。 |
| [`tools/theme.sh`](tools/theme.sh) | 把 [`themes/`](themes/) 下的一个文件夹推送到 launcher，并重启主屏幕。 |
| [`launcher/build-and-install.sh`](launcher/build-and-install.sh) | 构建精简后的安装包（约 300 KB），完成安装并切换主屏幕；如果主屏幕没有落到新 launcher 上，会自动回滚。 |

传给 `disable.sh` 和 `restore.sh` 的 debloat 清单路径按你运行命令所在目录解析，因此你自己的清单可以放在仓库之外，绝对路径同样可用。

每个脚本旁边都有一个对应的 PowerShell 版本。Windows 上装好 Android Studio 后就无需其他依赖：

```powershell
python -m venv tools\venv; tools\venv\Scripts\python.exe -m pip install -r tools\requirements.txt
powershell -ExecutionPolicy Bypass -File launcher\build-and-install.ps1 -TvHost 192.168.1.50
powershell -ExecutionPolicy Bypass -File tools\disable.ps1 -TvHost 192.168.1.50 examples\xiaomi-mi-tv-4a\debloat.txt
```

安装脚本会先问电视主屏幕当前归哪个 launcher 所有，并且只停用它能识别的那个（`tvlauncher` 或 `launcherx`）；如需手动指定请传 `STOCK_LAUNCHER=<package>`（PowerShell 为 `-StockLauncher`），传 `none` 则完全不动它。

## launcher 详解

一个小巧的原生 Android TV 应用（`com.gathin.tvhome`，安装后约 300 KB），用朴素的 Java 和 AndroidX RecyclerView 写成，没有引入任何更重的东西。专为 1 GB 内存的电视打造：无模糊、无视频、无联网、无后台服务。构建需要 JDK 17 和 Android SDK platform 34；在 macOS 上执行 `brew install openjdk@17 android-commandlinetools` 和 `sdkmanager "platforms;android-34" "build-tools;34.0.0"`。在 Linux 上，安装脚本会自动找到 `~/Android/Sdk` 以及 PATH 中的 `java`。

- 在 [`config.xml`](launcher/app/src/main/res/values/config.xml) 里**配置**：dock 顺序、隐藏应用、Live TV 包名、列数（从 5 列起磁贴开始缩小）、dock 下方的行数、网络胶囊里可选展示的 VPN 应用，以及为 GPU 跟不上的电视准备的 `reduced_motion`。
- **电视端 launcher 设置：**点击 Settings 进入电视的系统设置；或在 Settings 上长按 OK 键并选择 Launcher settings，可设置每行 4、5、6 或 7 个应用、开或关动画，以及选择启用高级特效。高级特效会增加磁贴抬起、图标缩放和平滑的环境色过渡；可能占用更多内存。选择 Follow theme 可清除电视端的选择；推送或重置主题也会清除它们。
- **更换默认主屏幕：**Launcher settings 和可选的 Default-home 磁贴（`show_home_settings_shortcut`）会打开 Android 的主屏幕选择器。选原来的 launcher 即可不再用 CleanYourTV 作主屏幕，选 CleanYourTV 则换回来。原来的 launcher 必须处于启用状态；如果安装脚本停用了它，请先用下文的恢复脚本。有些电视不提供主屏幕选择器。
- **主题**通过推送到电视的 `config.json` 设置上述同一批键值，外加背景色和壁纸，无需重新构建。[`themes/`](themes/) 内置三套主题，文档见该目录。
- **语言**跟随电视系统：英语、德语、西班牙语、加泰罗尼亚语、法语、俄语、塞尔维亚语（拉丁）、波兰语、葡萄牙语、土耳其语、阿拉伯语、希伯来语、简体中文、泰语。Android 13+ 可单独为 launcher 指定语言：`tools/tv.py 'cmd locale set-app-locales com.gathin.tvhome --locales ca'`。
  希伯来语下，菜单按钮位于左侧，日期和时钟位于右侧，问候语在时钟上方。Clock 屏保的日期与时间右对齐，希伯来语日期带有月份前缀 ב（例如 19 באוקטובר）。希伯来语的 dock 和应用网格行从右侧开始，遥控器的左右导航随之镜像。希伯来语的输入源选择器将图标和标签放在右侧、状态放在左侧，下拉菜单与 Inputs 按钮右缘对齐。其他语言保持原有布局。
  俄语包含模块卡片的批准与管理界面，以及 VPN 关闭徽章。
- **模块卡片**让任何电视应用都能声明自己的磁贴（标签、说明文字、光晕）。launcher 会就每个应用询问你一次，默认"保持隐藏"，并按该应用的签名密钥和卡片名记住答案。想改主意，长按 Settings 上的 OK 键并选择 Module cards。制作方法：[`docs/modules.md`](docs/modules.md)；接口契约：[`docs/specs/card.md`](docs/specs/card.md)。
- **Clock 屏保**：光晕之上缓缓漂移的时钟，杜绝烧屏。在电视的屏保设置里选择"Clock"，或通过 ADB：
  `tools/tv.py 'settings put secure screensaver_components com.gathin.tvhome/.ClockDream; settings put secure screensaver_enabled 1'`
- **遥控器按键**：一个可选的无障碍服务让遥控器的 Input 键在 Google TV 上继续可用（安装时设 `INPUT_KEY_SERVICE=1`）；另一个服务修复某些电视棒 Home 键被误发为 ALL_APPS 的问题，并支持用遥控器的齿轮键打开 Settings——哪怕是 Android 没有映射的键也行（`HOME_KEY_SERVICE=1`，scancode 或 keycode 在 `config.xml` 里配置）。
- **导航**经过精心设计：上、下键一次移动一行；顶部按钮绝不会让焦点落到磁贴上，从它们按"下"会回到你来时所在的 dock 磁贴；最后聚焦的应用会被记住；主屏幕开着时安装或卸载应用会立即刷新磁贴。
- **应用海报**：应用横幅以 xhdpi 或更高分辨率加载，这样低密度的电视 UI 就不会在聚焦放大之前先把它们降采样。

## 恢复你的电视

请保管好你应用的那份清单。恢复脚本会精确重新启用其中的包，把原装 launcher 放回主屏幕，并重置动画缩放：

```bash
TV_HOST=192.168.1.50 tools/restore.sh examples/<your tv>/debloat.txt                                    # Android TV
TV_HOST=192.168.1.50 tools/restore.sh examples/<your tv>/debloat.txt com.google.android.apps.tv.launcherx  # Google TV
```

它会把新 launcher 留在电视上（不想留就到电视的 设置 → 应用 里移除），也不感知你在清单之外停用的包。以后想换回去，重新运行一次安装脚本即可；即便主屏幕已经回落到 Android 的选择器，它也能判断出该停用哪个 launcher。如果电视已经连不上，电视自带的 设置 → 应用 页面同样可以重新启用这些包。

## 出问题怎么办

我们踩过的坑完整记录在 [docs/TROUBLESHOOTING.md](docs/TROUBLESHOOTING.md)。最要紧的三条：

- **macOS 在"本地网络"隐私限制下会拦截 `adb connect`**（报"No route to host"）。`tools/tv.py` 不依赖这个二进制，可以绕开。
- **务必等新 launcher 安装并运行之后再停用原装 launcher**，否则主屏幕会落到某个工厂测试应用上。安装脚本已替你排好顺序。
- **在 Google TV 上，设置向导**（`com.google.android.tungsten.setupwraith`）会在原装 launcher 被停用后抢走主屏幕，并让系统陷入崩溃循环。把它也停用，并写进你的 `debloat.txt`，这样恢复时才能一并还原。但请先检查 `dumpsys wifi | grep -o 'cname=[^ ]*'`：如果 Wi-Fi 网络是在设置向导里保存的，它就归 setupwraith 所有，停用它会把这条网络一并删掉（先在设置里重新加入网络；在那之前 `tools/disable.sh` 会跳过 setupwraith）。已经卡住了？执行 `tools/tv.py 'pm enable --user 0 com.google.android.apps.tv.launcherx'`。

## 常见问题

**安全吗？会把电视变砖吗？**不会刷写、root 或删除任何东西；包只是在用户空间里被停用。真正的风险是停用了电视赖以运行的东西，所以清单都是小批量应用，并随时备好恢复脚本。即使没有这些工具，电视自带的 设置 → 应用 页面也能重新启用这些包。

**固件更新怎么办？**大多数清单会停用更新服务，所以只有当你重新启用它时更新才会到来。万一装上了，最坏的情况也不过是某个包又回来了，再跑一遍脚本就行。

**应用会不会坏掉？**流媒体应用照常通过 Play 商店更新，而商店本身不受影响。launcher 只是列出已安装的应用，并用十年来一直稳定的 intent 去启动它们。

**能帮住在另一个家的人弄吗？**可以，通过一条私密的 [Tailscale](https://tailscale.com) 链路而非同一 Wi-Fi：要么在对方的电视上装 Tailscale 并共享给你，要么用对方家里的一台电脑或 Apple TV 路由过去。绝不要靠在对方的路由器上开放 ADB 端口来实现。分步做法见 [docs/REMOTE.md](docs/REMOTE.md)。

**开放 ADB 访问难道不是安全漏洞吗？**它只是在电视上明确点一次"允许这台电脑"，和开发 Android 应用一样。网络 ADB 在 5555 端口上是明文传输，而在带 `ro.adb.secure=0` 的固件上，局域网内的任何设备都能拿到 shell，所以用完请关掉：

1. 在电视上：开发者选项 → 关闭 **USB 调试**和 **网络/ADB 调试**，并撤销 USB 调试授权。
2. 重启电视，然后在你的电脑上确认端口已经关掉：`nc -vz <tv ip> 5555` 必须连接失败。

关掉调试之后，launcher 依然照常工作。

**应用内的广告也能拦吗？**可以拦一部分，用 Android 的私人 DNS（Private DNS，Android 9 及以上）。把它指向 [AdGuard DNS](https://adguard-dns.io) 这类拦截广告的解析器后，全系统所有应用的广告与跟踪域名都无法解析，重启后依然生效。代价是：这个解析器随后能看到电视发出的每一个 DNS 查询。

```bash
tools/tv.py 'settings put global private_dns_specifier dns.adguard-dns.com'
tools/tv.py 'settings put global private_dns_mode hostname'
```

它去不掉 YouTube 广告，因为广告和视频来自同一批服务器。如果有应用放不出来，或者电视提示"无互联网"（解析器宕机或不可达），用 `tools/tv.py 'settings put global private_dns_mode opportunistic'` 切换回去。

**AirPlay 呢？**本仓库不做。Android 手机可以继续用内置 Chromecast 投屏。iPhone 的话，[jqssun/android-airplay-server](https://github.com/jqssun/android-airplay-server) 可行；[PR #84](https://github.com/Gathin23/cleanyourtv/pull/84) 里有它的安装脚本。

**能直接下载 APK 吗？**用那条一行命令的脚本自己构建，只要一分钟，而且上你电视的东西由你把关。不提供预编译二进制。

## 参与贡献

最有用的贡献是你电视的 debloat 清单，让下一个同型号用户不必重新摸索。launcher 的改进和更精炼的 prompt 措辞也同样欢迎。格式和我们要求的测试见 [CONTRIBUTING.md](CONTRIBUTING.md)。在上面构建了点什么——一个 launcher、一个移植、一套主题？把它加进 [SHOWCASE.md](SHOWCASE.md)，那里已经有十一个项目：LG 的 webOS 移植、一个 Stremio shelf、一个 Hisense 换肤、若干 Fire TV launcher、一个 AirPlay 安装器。

本仓库凝结着以下这些人的工作：

<a href="https://github.com/Gathin23/cleanyourtv/graphs/contributors"><img src="https://contrib.rocks/image?repo=Gathin23/cleanyourtv&columns=16" alt="Contributors"></a>

<details>
<summary><strong>Star 历史</strong></summary>

<a href="https://star-history.com/#Gathin23/cleanyourtv&Date"><img src="https://api.star-history.com/svg?repos=Gathin23/cleanyourtv&type=Date" alt="Star history chart" width="640"></a>

</details>

## 许可证

MIT，见 [`LICENSE`](LICENSE)。Outfit 字体遵循 SIL Open Font License 授权，见 `launcher/FONT-LICENSE-OFL.txt`。
