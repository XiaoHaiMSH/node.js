# 自用 OpenWrt 固件与插件源

## 插件包

- https://github.com/XiaoHaiSly/openwrt-packages.git

个人维护的自用插件源，固件预置使用，每日定时更新。

## 上游固件源码

- LibWrt：https://github.com/LiBwrt/LibWrt.git
- VIKINGYFY：https://github.com/VIKINGYFY/immortalwrt.git

用于 CI 编译的上游源码，按目标设备选择。

## 固件说明

- 内置与当前固件内核 ABI 匹配的 kmod 软件源，提供编译产出的内核模块。
- 预置个人维护的插件软件源，每日定时更新。
- 每天 05:00 自动编译；固件信息中的时间为编译开始时间，便于核对上游源码提交时间。
- 支持 MediaTek、Qualcommax 系列设备。

## 目录说明

- `.github/workflows`：GitHub Actions CI 配置
- `scripts`：自定义脚本
- `config`：编译配置
