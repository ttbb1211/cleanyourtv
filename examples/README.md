# 示例

每个电视型号对应一个文件夹，里面各有一份 `debloat.txt`，按组分类并附有注释，
列出在该固件上可以安全停用的软件包。这些清单只是起点：请把自己在用的软件包注释掉。

| 目录 | 电视 | 系统 | 说明 |
|---|---|---|---|
| `aipro2k/` | AiPro2K（Expressluck，dongnae；Changhong AI PONT 系列） | Android TV 14 | Anoki ACR、Google 广告服务、零售演示和 Wi-Fi Display 测试应用；1 GB；setupwraith 必须随 launcherx 一起停用（否则 Home 会回落到它的 RecoveryActivity）；保留 CVTE/Expressluck 出厂软件包和 `com.epl.hotkey` |
| `amazon-fire-tv-stick-4k-2018/` | Amazon Fire TV Stick 4K，2018 年第一代（AFTMM，mantis） | Fire OS 6.7.1.1 / Android 7.1 | 首个 Fire OS 6 清单：Amazon 遥测、广告/推荐数据源、Live 标签页和 Fire TV Channels、Shopping、Kids、Music/Photos/Silk、全屋音频、Alexa 附加组件；未使用的流媒体应用按个人选择关闭；已注明十个受保护软件包；保留语音搜索、OTA 和投屏；仅做 debloat，赞助推荐行需要配合 DNS 屏蔽 |
| `benq-e55-735/` | BenQ E55-735（Changhong AI PONT，DVB96BQ） | Google TV 14 | Homwee 商店/帮助、Anoki ACR、Google TV 推荐内容；含无线调试配对、setupwraith、深度待机的说明 |
| `chiq-gtvu65/` | CHiQ AI PONT（Changhong GTVU65，dangni，MediaTek mt5867） | Google TV 14 | Google 广告服务和自动安装、Homwee 商店/帮助；1 GB；setupwraith 必须停用（RecoveryActivity 组件无法单独停用）；MediaTek partnercustomizer 可安全停用（已重启验证） |
| `chiq-ai-pont/` | CHiQ AI PONT（DVB93CQ） | Android TV 11 | Anoki ACR、FAST 频道、AI PONT、Homwee 服务 |
| `google-chromecast-gtv-4k/` | Chromecast with Google TV 4K（sabrina） | Google TV 14 | Google 遥测和广告服务、环境模式、launcherx + setupwraith；无线调试配对、YouTube 按键重映射 |
| `hisense-hismarttv-a4/` | Hisense HiSmartTV A4（xiaoyushan，MStar m7322），印度 | Android TV 9 | Hisense 日志上报、首页赞助推荐行、商店演示、预装应用自动安装、OTA；USB 调试会打开 5555 端口，没有无线调试开关；保留 smartsense |
| `hisense-smarttv-4k-ffm/` | Hisense SmartTV 4K FFM（huangshan，MediaTek） | Android TV 10 | ACR（evservice）、VIDAA 预装应用、商店/酒店模式、OTA；smartsense 必须保持启用 |
| `hisense-u75-hengshan/` | Hisense U75（hengshan，MediaTek），拉丁美洲 | Google TV 12 | Vtp_ACR 内容识别、VIDAA Channels Plus 及内容标签页、Family Moment、商店/酒店/工厂模式、DeviceAssistant 清理器、Ginga 广播中间件、Google PAI 自动安装；按个人选择保留 OTA、投屏和全部流媒体应用；smartsense/AIoT 系列必须保留（有 Recovery 风险） |
| `hitachi-65qledsm20/` | Hitachi 65QLEDSM20（MTC，bangbae，MediaTek m7322），澳大利亚 | Android TV 11 | Anoki ACR 和 FAST 频道、JVC 自动安装；"demo" 软件包负责 Input 键和遥控器配对；1.3 GB |
| `insignia-ns55f301na25/` | Insignia 55" F30 4K Fire TV（NS-55F301NA25，AFTDCT31，duckie） | Fire OS 7 / Android 9 | Amazon ACR 遥测、Fire TV 广告/购物、Alexa、OTA 更新；保留 AirPlay 和 TIF HDMI 输入源 |
| `nvidia-shield-tv-pro-2019/` | NVIDIA SHIELD TV Pro 2019（P2897，mdarcy） | Android TV 11 | NVIDIA 遥测、GameStream 残留、赞助推荐行、合作伙伴自动安装 |
| `oneplus-tv-dubai/` | OnePlus TV（D00，Dubai） | Google TV 14 | HeyTap/OnePlus 附加组件、OnePlus Connect、Smart Home |
| `panasonic-4ktv-jup/` | Panasonic 4KTV-JUP（Jupiter_PA，MediaTek） | Android TV 11 | Google 推荐行和屏保、Panasonic 演示/酒店/帮助应用、日历/打印/备份残留；流媒体应用按个人选择关闭；保留 `com.mediatek.*` |
| `philips-50pus8517/` | Philips 50PUS8517/12（TP Vision，PH1M_EA_9970A，MediaTek MT5895），欧洲 | Android TV 11 | 首个 `org.droidtv` TP Vision 清单：DAC 分析数据上传器（AWS Firehose）、Top Picks、应用商店；Assistant、DLNA、IP 控制按个人选择关闭；停用 `eum` 或 `aurora` 后 `xtv` 会永远不停地重试，且 `eum` 还会连带杀掉信号源抽屉——见怪癖 5 |
| `philips-55pus7503/` | Philips 55PUS7503/12（TP Vision TPM171E，PH7M_EU_5596，MediaTek MT5891），欧洲 | Android TV 8.0 | 偏保守的老一代清单：Philips 演示、Top Picks 和使用情况记录；Google 推荐/教程；保留语音、Chromecast、系统更新、Ambilight 和全部流媒体应用 |
| `philips-r8g-google-tv/` | Philips R8G Google TV（MOKA，whitefield，Realtek RTD2851F），美国 | Google TV 14 | Anoki ACR、商店演示覆盖层、Realtek 合作伙伴定制器、HbbTV（使用 ATSC 时用不到）、Android 广告服务；语音和环境模式按个人选择关闭；无需配对即会打开 5555 端口；setupwraith 占有设置时保存的 Wi-Fi，停用它会把该网络一并删除 |
| `philips-smart-4k-google-tv/` | Philips Smart 4K TV（Skyworth，eleonas，MediaTek），印度 | Google TV 14 | Skyworth 推荐、售后/激活追踪器、iCast；Chromecast、Assistant 按个人选择关闭；无线调试配对、setupwraith |
| `prismplus-q65-ultra-r10g/` | PRISM+ Q65 Ultra 2026 QLED 4K AI Google TV（R10G，PRISMPLUS_FFM，MOKA，Realtek RTD2875 SoC，RTD6748 平台） | Google TV 14 | Realtek 合作伙伴定制器、Google partner setup 和自动安装、环境模式、未使用的 DTMB/ISDB/ATSC 调谐器、卡拉 OK、预装应用；Max 按个人选择关闭；保留 com.realtek.dtv 和 com.realtek.tv.atv 以保障信号源 |
| `rca-ai-pont/` | RCA AI PONT SA（Changhong，redwood，ISDB92RC；也以 realme 40 英寸版本销售） | Android 14 | Homwee 商店和安装器、Anoki ACR、FAST 频道；1 GB |
| `redmi-mitv-antl0/` | Redmi TV（MiTV-ANTL0，starwars） | Android 5.1.1（非 Android TV） | Mi 推送/网页内容/云控制广告、TV Taobao、系统自带屏保、OTA；需要用 `pm hide` 而非 `pm disable-user`，开机广告是一个 `setprop` |
| `sanyo-atv-r2/` | SANYO ATV R2（SCBC，Realtek RTD285O） | Android TV 9 | S-Channels、E-SHOW 演示、Vewd、TV Booster、SANYO OTA |
| `skyworth-swtv-21ae/` | Skyworth SWTV-21AE（sunnyvale，MediaTek） | Android TV 14 | Skyworth 首页行定制器、商店演示、电子手册；Google 反馈；FAST 频道、YouTube、环境模式按个人选择关闭；无需配对即会打开 5555 端口；1 GB |
| `skyworth-swtv-24na-4k-nf/` | Skyworth SWTV-24NA-4K NF（eleonas，MediaTek mt5896），美国 | Google TV 14 | 与印度版 Philips Smart 4K 同平台：Skyworth 推荐、售后/激活追踪器、合作伙伴定制器、Ginga/MHEG；按个人选择保留投屏、卡拉 OK 和 OTA；仅支持无线调试配对；setupwraith 占有设置时保存的 Wi-Fi，停用它会把该网络一并删除 |
| `sony-bravia-ae2/` | Sony BRAVIA 4K AE2（BRAVIA_AE2，MediaTek MT5897），北美 | Google TV 14 | Samba TV、Sony 代理/推广/Select、演示模式、ATSC 调谐器在北美以外用不到；launcherx + setupwraith；无线调试配对、屏保相关说明 |
| `sony-bravia-4k-gb/` | Sony BRAVIA 4K GB（BRAVIA_ATV2_EU，BRAVIA_ATV2） | Android TV 9 | Samba TV ACR、Sony Select/推广/Discover、演示模式、设备代理；与 X900E 使用相同固件；特意保留 Chromecast、镜像投屏、DLNA 和 USB 媒体 |
| `sony-bravia-4k-ur2/` | Sony BRAVIA 4K UR2（BRAVIA_UR2_4K，MediaTek） | Android TV 10 | Samba TV、Sony 推广/Select、演示模式；Assistant、Chromecast、未使用的流媒体应用按个人选择关闭 |
| `sony-bravia-4k-vh2/` | Sony BRAVIA 4K VH2（KD-55X80J，BRAVIA_VH2，MediaTek），欧盟 | Google TV 12 | Samba TV ACR、Sony/Qterics 设备代理、演示模式、帮助卡片；为使用自定义启动器而停用 setupwraith；保留 Assistant、Chromecast 和固件更新 |
| `sony-bravia-9-ii/` | Sony BRAVIA 9 II（K-65XR90M2，BRAVIA_AE3，MediaTek MT5838） | Google TV 14 | Samba TV ACR、Sony/Qterics 设备代理、IDD、My BRAVIA 推广、Sony Select 和 Sony 标签页、演示模式；为使用启动器而停用 setupwraith，但它占有设置期间保存的 Wi-Fi，停用它会把该网络删除；Chromecast 按个人选择关闭 |
| `sony-bravia-bf1/` | Sony BRAVIA BF1（BRAVIA 2 II 级别，BRAVIA_BF1_4K_A，MediaTek） | Google TV 12 | Samba TV、Sony 推广/Select、演示模式、预装应用；分步骤切换 Home（涉及 setupwraith）、环境屏保、applicationdisabler 会重新启用 IoT |
| `sony-kd-55x85j/` | Sony BRAVIA KD-55X85J（2021 年，BRAVIA_VH2，MediaTek MT5895），南美洲 | Google TV 12 | 与 VH2 欧版清单为同一构建；Samba TV ACR、Sony/Qterics 代理、IDD、Sony 推广/Select/标签页、合作伙伴自动安装、演示模式；没有该服务 Input 键也能用；换装启动器后停用 setupwraith、launcherx 和 dreamx，屏保为 ClockDream；已重启验证 |
| `sony-kd-65x80j/` | Sony BRAVIA KD-65X80J（2021 年，BRAVIA_VH2，MediaTek），印度 | Google TV 10 | Samba TV、Sony 设备代理、Sony Select/标签页、酒店模式服务、BRAVIA CAM 残留；为使用自定义启动器而停用 setupwraith；4 GB 的 /data 会满，安装前先清理缓存 |
| `sony-xbr-x900e/` | Sony BRAVIA XBR-65X900E（2017 年，BRAVIA_ATV2） | Android TV 9 | Samba TV ACR、Sony Select、My BRAVIA 推广、Discover、设备代理；Chromecast、DLNA、镜像投屏按个人选择关闭 |
| `stellamore-t950s/` | Stellamore T950S 投影仪（Droidlogic be30a3，Amlogic txhd2） | Android 13 | Zeasn 应用商店和系统自带启动器都捆绑了 Google Ads（doubleclick）；Zeasn 设备门户/OTA、Stellamore 工厂/测试/指南应用；1 GB；梯形校正必须保持启用 |
| `tcl-40s5400a/` | TCL 40S5400A（C06，C06_2K_GB，MediaTek MT9221，1 GB） | Android TV 11 | TCL 账号/TGuard/推广行、USB 播放器、语音和照片屏保按个人选择关闭；ttvs 是固件更新器，必须保留；系统自带启动器持有 HOME 优先级 2，因此必须停用 |
| `tcl-43c645/` | TCL 43C645（Smart TV Pro，Realtek RTD2851 / R51MT05，V8-R51MT05-LF1V652） | Android TV 11 上的 Google TV 启动器 | TCL BI 分析/推广、Google 合作伙伴底层组件、setupwraith（系统自带启动器停用后会抢占 HOME）；保留语音和 Chromecast，固件更新器和 Miracast 按个人选择关闭；已在真机上测试，启动器可用 |
| `tcl-50ep680/` | TCL 50EP680（欧洲，BeyondTV，Realtek rtd285o） | Android TV 11 | TCL 分析 + 内容信息流、giftbox 仪表盘、合作伙伴定制器、预装游戏/新闻；英国 Freeview 应用出厂时即已关闭；语音按个人选择关闭；启动器可用（原装启动器 `com.google.android.tvlauncher`，Live TV 为 `com.tcl.tv`） |
| `tcl-g10-google-tv/` | TCL 55" 4K Google TV，2023 年（G10，G10_4K_US_NF）；另有 TCL 55P6K，西班牙（G10_4K_GB_NF_32BIT） | Google TV 12 | TCL TV+、TCL Live、商店演示、smartlink 安装器；系统自带启动器停用后，setupwraith 也会抢占 Home |
| `tcl-q10g-pro/` | TCL 55Q10G Pro（中国，tcl_mt5879_cn，MediaTek MT9952） | Android TV 11 | 无 Google 服务，TCL 开机广告 + 分析/BI，OTA 和账号服务；ADB 要在 Device info 界面按 UP/DOWN/LEFT/RIGHT 才会打开，而不是通过版本号；仅做 debloat，系统自带启动器无法替换（安装时校验签名） |
| `tcl-65c725/` | TCL 65C725（Smart TV Pro，BeyondTV4） | Android TV 11 | TCL 分析/推广、Google 推荐行；语音已关闭，OTA 按个人选择关闭 |
| `tcl-65c735/` | TCL 65C735（Smart TV Pro，G05，MediaTek），法国 | Google TV 11 | TCL 分析、TGuard、推广仪表盘和内容信息流、未使用的预装应用；语音和 AirPlay 按个人选择关闭，保留 Chromecast 和 Miracast；launcherx + setupwraith 已停用（重启后仍保持停用）；遥控器应用的按键需要 launcherx（已注明键值码）；开启 USB 调试时重启后 USB 端口会进入 gadget 模式 |
| `tcl-ak30a5/` | TCL ak30a5（中国，Amlogic） | Android TV 9 | 无 Google 服务，TCL 开机广告 + 分析，无 TvInputManager，只能经 USB 安装应用；仅做 debloat，此固件无法安装第三方启动器 |
| `tcl-beyondtv/` | TCL BeyondTV（印度） | Android TV 9 | TCL 分析、内容信息流、TCL 应用商店、Google 推荐行；Jio/Airtel/Hotstar 应用未作改动 |
| `tcl-beyondtv-rt2851/` | TCL BeyondTV，欧盟/北欧（Realtek RTD2851，V8-R851T02-LF1V606） | Android TV 9 | TCL BI 分析、推广行、cyberui、清理器和商店；镜像投屏、语音和固件更新器按个人选择关闭；保留 Chromecast；appmarket2/tvweishi 有专门的安装说明 |
| `tcl-beyondtv2-latin-america/` | TCL BeyondTV2（拉丁美洲/巴西，Realtek RTD2851） | Android TV 9 | TCL 分析和开机内容信息流；`com.tcl.esticker` 在此固件上无法保持停用；英国 Freeview 应用出厂时即已关闭 |
| `tcl-qm6k-google-tv/` | TCL QM6K Pro，2025 年（G08，MediaTek tcl9618） | Google TV 14 | Samba TV ACR（ttvs）、TCL TV+、TCL Live、商店/酒店演示；要换自定义启动器就必须停用 setupwraith（另见 AU14、#23） |
| `tcl-g05-google-tv/` | TCL Smart TV Pro（G05，G05_4K_US，MediaTek MT5889） | Google TV 11 | TCL Channel、waterfall、ttvs BI、TGuard；快捷面板按个人选择关闭；setupwraith 在重启后自行恢复，启动器效果一半未经验证 |
| `tcl-uniontv-latin-america/` | TCL UnionTV，拉丁美洲（TCL 制造，类似 Thomson 32HE5800，Realtek RT2841） | Android TV 9 | TCL BI 分析、推广行/合作伙伴定制器、应用商店、清理器、用户中心；环境模式、TTS、TalkBack 和语音已关闭；保留 Chromecast 和固件更新器；待机（STR）会断开以太网，无法通过网络唤醒 |
| `thomson-32he5800/` | Thomson 32HE5800（TCL 制造的 UnionTV，Realtek RT2841），西班牙 | Android TV 9 | TCL BI 分析、TCL 应用商店/用户中心、TV Guard 清理器、Google 推荐行；1.4 GB 低内存机型；语音、USB 媒体播放器按个人选择关闭 |
| `toshiba-fire-tv-aftha004/` | Toshiba Fire TV（AFTHA004，hazel） | Fire OS 7 / Android 9 | Amazon ACR、指标上报、购物、教程、Miracast 接收端；流媒体预装应用按个人选择关闭；仅做 debloat |
| `vu-4k-lushan/` | Vu 4K（HVCL，lushan，MediaTek），印度 | Google TV 12 | Vu/Hisense ACR（evservice）、商店模式、Alexa、Vu 预装应用、合作伙伴自动安装；保留 smartsense/aiot，为使用启动器而停用 setupwraith |
| `xgimi-horizon-s-pro/` | XGIMI Horizon S Pro 投影仪（XK03H，xgimigalileo，MediaTek） | Android TV 11 | 首个投影仪型号：保留梯形校正/自动对焦/HDMI 播放器，工厂和老化测试工具、bug 报告上传器、Google 预装应用；HDMI 需要 `input_action`；语音、Chromecast 按个人选择关闭 |
| `xiaomi-mi-box-s/` | Xiaomi Mi Box S（MIBOX4，oneday），流媒体盒子 | Android TV 9 | PatchWall、Mi 分析、Alphonso 广告追踪、MiLink；语音、投屏、手机遥控按个人选择关闭 |
| `xiaomi-mi-box-s-2nd-gen/` | Xiaomi Mi Box S 第二代（MiTV-AFKR0，jaws），流媒体盒子 | Google TV 11 | Mi 广告行和 PatchWall、Mi 分析、合作伙伴自动安装、更新服务按个人选择关闭；为使用启动器而停用设置向导，注意 Wi-Fi 密码需要重新输入 |
| `xiaomi-mitv-mooq0/` | Xiaomi Mi TV（MiTV-MOOQ0，croods） | Android TV 10 | PatchWall、Mi 分析、MiChannel、TV Manager、Alexa 桥接；工厂测试应用也会抢占 HOME；说明来自 #81 |
| `xiaomi-mi-tv-4a/` | Xiaomi Mi TV 4A（MiTV-MOOQ1） | Android TV 10 | PatchWall、Mi 分析、SmartShare、MiLink |
| `xiaomi-mitv-aesp0/` | Xiaomi MiTV-AESP0 电视棒（aquaman，1 GB） | Android TV 9 | 无输入源；Home 键会触发 ALL_APPS，需要 `HOME_KEY_SERVICE=1`；保留 Chromecast |
| `xiaomi-mitv-astp1/` | Xiaomi MiTV-ASTP1（maverick），中国固件 2.40.641.0514.cn，1 GB 内存，720p | Android TV 9（CN 版） | 首个 CN 固件小米机型：无 Google 应用；系统自带启动器为 `com.mitv.tvhome`（需传入 `STOCK_LAUNCHER`）；每次重启后 ADB 都会关闭；Mi 分析/推送/广告、商店插件、TV Manager、更新器已关闭；保留投屏和应用商店 |
| `xiaomi-mitv-axfr1/` | Xiaomi MiTV-AXFR1（rango，Amlogic，1 GB），印度 | Android TV 11 | PatchWall、Mi 分析、赞助推荐行、合作伙伴自动安装、TV Manager；镜像投屏、OTA 和未使用的流媒体应用按个人选择关闭；保留 Chromecast 和语音；PatchWall 的输入源弹窗用不到（输入源选择器来自 Live TV）；可使用自定义 HOME，setupwraith 不会抢占 HOME |
| `xiaomi-mitv-axso0/` | Xiaomi MiTV-AXSO0（dangal；Mi TV 4C Pro 2019 / 4A Pro） | Android TV 9 | PatchWall、Glance 广告、Mi TV+、Sensara、Mi 分析、MiLink；语音、Chromecast、未使用的流媒体应用按个人选择关闭 |
| `xiaomi-mitv-moor2/` | Xiaomi MiTV-MOOR2（venom，MediaTek） | Google TV 11 | Mi 广告行和 PatchWall、Mi 分析、MiLink、商店演示；停用设置向导，让第三方启动器接管 Home |
| `xiaomi-mitv-mosr4/` | Xiaomi MiTV-MOSR4（irobot，MediaTek） | Google TV 11 | Mi 广告行和 PatchWall、Mi 分析、TV Manager、Miracast 接收端、OTA 按个人选择关闭；停用设置向导，让第三方启动器接管 Home；`overseaservice` 承载 Netflix 键，必须保留 |
| `xiaomi-mitv-mssp3/` | Xiaomi MiTV-MSSP3（machuca，MediaTek） | Android TV 11 | PatchWall、Mi 分析、Netflix 观察器；Chromecast、屏保、未使用的流媒体应用按个人选择关闭 |
| `xiaomi-mitv-mssp3-android9/` | Xiaomi MiTV-MSSP3（machuca，MediaTek），Android 9 固件 PI.7524 | Android TV 9 | 同一机型在 Android 11 更新前的固件：PatchWall、Mi 分析、TV Manager、OTA；语音助手每次开机会自行重新启用（系统应用更新后重新扫描所致）；屏保、预装应用已关闭；1.8 GB，此前 swap 已满 |
| `xiaomi-tv-a-pro-2026/` | Xiaomi TV A Pro 75" 2026（MiTV-MZTU0，river，MediaTek） | Google TV 14 | PatchWall/Mi Home 标签页、Mi 分析、TV Manager、更新器；设置向导已停用，有 launcherx 崩溃循环的说明 |
| `xiaomi-mitv-afmu0/` | Xiaomi TV Box S 第三代（MiTV-AFMU0，twilight，Amlogic），流媒体盒子 | Google TV 14 | Mi 分析、PatchWall/Mi Home 标签页、Mi connect/SmartShare；语音和手机遥控按个人选择关闭；停用设置向导，以便装上 launcherx |

尚未有已测试清单的型号，其说明存放在 [`docs/devices/`](../docs/devices/) 中（Xiaomi MiTV-MFTR0 "freeguy"，中国，Android 14：输入源、Xiaomi 设置 intents、应用发现）。

想添加你的电视，请参阅 [CONTRIBUTING.md](../CONTRIBUTING.md)。获取一份清单最快的方式，是
运行 [PROMPT.md](../PROMPT.md) 中的提示词，然后把你的助手停用的软件包复制过来。
