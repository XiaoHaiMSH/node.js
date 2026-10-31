<div align="center">

# OpenWrt 自用固件

**个人自用 · 每日自动编译 · 内置完整 kmod 源**

<sub>MEDIATEK 系列 · QUALCOMMAX 系列</sub>

</div>

---

## 📦 自用插件包

> 个人维护的自用插件源，配合固件使用。

- **仓库地址**：<https://github.com/XiaoHaiSly/openwrt-packages>

---

## 🔧 OpenWRT-CI

固件基于以下上游仓库构建：

| 上游仓库 | 地址 |
| :-- | :-- |
| **LibWrt** | <https://github.com/LiBwrt/LibWrt> |
| **VIKINGYFY** | <https://github.com/VIKINGYFY/immortalwrt> |

---

## ✨ 固件说明

| 项目 | 说明 |
| :-- | :-- |
| 🧩 **内核模块** | 内置配套 kmod 软件源，**完整提供全部内核模块** |
| 🛒 **插件软件源** | 预置个人维护的自用插件源，**每日定时更新** |
| ⏰ **自动编译** | 每天 **早上 5:00** 自动编译 |
| 🕐 **时间说明** | 固件信息中的时间为**编译开始时间**，便于核对上游源码提交时间 |
| 📱 **适配平台** | MEDIATEK 系列、QUALCOMMAX 系列 |

---

## 📁 目录结构

```
.
├── workflows/   # 自定义 CI 配置
├── Scripts/     # 自定义脚本
└── Config/      # 自定义配置
```

---

<div align="center">
<sub>⭐ 自用固件，按需取用</sub>
</div>
