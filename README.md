# OpenWRT-CI

自动编译的 OpenWrt 固件，每日更新。

## 📦 源码与插件

| 类型 | 仓库 |
| --- | --- |
| 自用插件包 | [XiaoHaiSly/openwrt-packages](https://github.com/XiaoHaiSly/openwrt-packages) |
| LibWrt | [LiBwrt/LibWrt](https://github.com/LiBwrt/LibWrt) |
| VIKINGYFY | [VIKINGYFY/immortalwrt](https://github.com/VIKINGYFY/immortalwrt) |

## ✨ 固件特性

- 内置配套 kmod 软件源，完整提供全部内核模块
- 预置个人维护的自用插件软件源，每日定时更新
- 每天早上 5 点自动编译
- 固件信息中的时间为编译开始时间，方便核对上游源码提交时间

## 🔧 支持平台

- MEDIATEK 系列
- QUALCOMMAX 系列

## 📁 目录结构

| 目录 | 说明 |
| --- | --- |
| `workflows` | 自定义 CI 配置 |
| `Scripts` | 自定义脚本 |
| `Config` | 自定义配置 |
