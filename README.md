# 自用插件包

| 项目 | 内容 |
| --- | --- |
| 插件包地址 | https://github.com/XiaoHaiSly/openwrt-packages.git |
| 说明 | 个人维护的自用插件软件源，固件预置使用，每日定时更新 |

# OpenWRT-CI

| 上游固件源码 | 地址 |
| --- | --- |
| LibWrt | https://github.com/LiBwrt/LibWrt.git |
| VIKINGYFY | https://github.com/VIKINGYFY/immortalwrt.git |

# 固件简要说明

| 项目 | 说明 |
| --- | --- |
| 内核模块 | 固件内置配套 kmod 软件源，提供全部内核模块 |
| 插件软件源 | 固件预置个人维护的自用插件软件源，每日定时更新 |
| 自动编译 | 固件每天早上 5 点自动编译 |
| 编译时间 | 固件信息里的时间为编译开始时间，方便核对上游源码提交时间 |
| 支持平台 | MEDIATEK 系列、QUALCOMMAX 系列 |

# 目录简要说明

```text
.
├── workflows/   # 自定义 CI 配置
├── Scripts/     # 自定义脚本
└── Config/      # 自定义配置
