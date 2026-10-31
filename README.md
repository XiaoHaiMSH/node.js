# OpenWrt-CI

个人维护的 OpenWrt / ImmortalWrt 固件编译项目，基于不同上游源码构建，集成自用插件及配套软件源。

## 项目仓库

### 自用插件软件源

[XiaoHaiSly/openwrt-packages](https://github.com/XiaoHaiSly/openwrt-packages)

个人维护的插件软件包，预置于固件中，并通过每日定时任务自动更新。

### 上游源码

| 项目 | 源码仓库 |
| :--- | :--- |
| **LibWrt** | [LiBwrt/LibWrt](https://github.com/LiBwrt/LibWrt) |
| **VIKINGYFY** | [VIKINGYFY/immortalwrt](https://github.com/VIKINGYFY/immortalwrt) |

## 固件特性

- **配套内核模块源**：固件内置与当前固件内核相匹配的 kmod 软件源，完整提供全部内核模块。
- **自用插件源**：预置个人维护的插件软件源，每日定时更新。
- **自动编译**：每天早上 05:00 自动触发固件编译。
- **编译时间标识**：固件信息中显示编译开始时间，便于核对上游源码提交时间及构建批次。

## 支持平台

- **MEDIATEK** 系列
- **QUALCOMMAX** 系列

## 项目目录

| 目录 | 说明 |
| :--- | :--- |
| `workflows/` | 自定义 GitHub Actions CI 配置 |
| `Scripts/` | 固件编译及运行相关的自定义脚本 |
| `Config/` | 固件编译配置及自定义配置文件 |

---

*本项目主要用于个人固件构建与维护。*
