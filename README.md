# 自用 OpenWrt 固件与插件包

## 固件说明

- 支持平台：MEDIATEK 系列、QUALCOMMAX 系列。
- 自动编译：每天早上 5:00 自动编译。
- 固件信息中的时间为编译开始时间，方便核对上游源码提交时间。
- 固件内置配套 kmod 软件源，完整提供全部内核模块。
- 固件预置个人维护的自用插件软件源，每日定时更新。

## 软件源 / 插件包

- 自用插件包：  
  https://github.com/XiaoHaiSly/openwrt-packages.git

## 上游源码 / OpenWRT-CI

- LibWrt：  
  https://github.com/LiBwrt/LibWrt.git
- VIKINGYFY：  
  https://github.com/VIKINGYFY/immortalwrt.git

## 目录说明

- `workflows`：自定义 CI 配置
- `Scripts`：自定义脚本
- `Config`：自定义配置
