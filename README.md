# OpenWrt Actions

基于 GitHub Actions 的 OpenWrt / ImmortalWrt 自动化固件编译项目，整合 LibWrt 与 ImmortalWrt 多套源码，支持 Qualcomm IPQ 和 MediaTek Filogic 平台。

## 项目特点

- **自建软件源**：本项目自行维护，包含官方未收录的插件及领先官方版本的更新
- **全量 kmod 收集**：固件内置配套的 kmod 与 packages 源，编译时全量收集本平台生成的 kmod
## 构建平台

| 源码 | 分支 | 支持平台 |
| --- | --- | --- |
| [LiBwrt/LibWrt](https://github.com/LiBwrt/LibWrt) | `25.12-nss` | Qualcomm IPQ60xx、IPQ807x |
| [VIKINGYFY/immortalwrt](https://github.com/VIKINGYFY/immortalwrt) | `owrt` | Qualcomm IPQ60xx、IPQ807x、MediaTek Filogic |

## 配套软件源


- **kmods**：目标平台本次编译生成的内核模块，按 subtarget 分类收录。
- **packages**：按配置清单收集的用户态软件包。

## License

[MIT License](LICENSE)
