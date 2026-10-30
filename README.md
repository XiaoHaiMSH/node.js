# OpenWrt Actions

基于 GitHub Actions 的 OpenWrt / ImmortalWrt 自动化固件编译项目，整合 LibWrt 与 ImmortalWrt 多套源码，支持 Qualcomm IPQ 和 MediaTek Filogic 平台。

## 项目特点

- **自带配套软件源**：固件编译完成后，自动收集并发布对应平台的软件包，无需用户自行寻找第三方 kmod 源。
- **全量 kmod 收集**：编译默认启用 `CONFIG_ALL_KMODS=y`，将目标平台本次构建生成的 kmod APK 集中收录到软件源，并按 subtarget 分类。
- **内核版本匹配**：每份 kmod 软件源都记录对应的 `vermagic`，发布前自动与固件内核校验，确保模块与固件匹配。
- **固件内置软件源**：编译时自动写入对应的软件源地址，刷入固件后即可使用，无需手动添加。
- **自动化构建发布**：自动完成源码获取、软件包整理、固件编译、APK 索引生成及 Cloudflare Pages 部署。

## 构建平台

| 源码 | 分支 | 支持平台 |
| --- | --- | --- |
| [LiBwrt/LibWrt](https://github.com/LiBwrt/LibWrt) | `25.12-nss` | Qualcomm IPQ60xx、IPQ807x |
| [VIKINGYFY/immortalwrt](https://github.com/VIKINGYFY/immortalwrt) | `owrt` | Qualcomm IPQ60xx、IPQ807x、MediaTek Filogic |

## 配套软件源

软件源由项目自动构建并发布到 Cloudflare Pages，分为两部分：

- **kmods**：目标平台本次编译生成的内核模块 APK，按 subtarget 分类收录。
- **packages**：按配置清单收集的用户态软件包。

固件会自动写入对应的软件源配置：

```text
/etc/apk/repositories.d/extra-feeds.list
```

**注意：kmod 与内核版本严格绑定。** 请使用固件内置的软件源，不要混用其他源码、分支或内核版本的软件模块。项目会在发布前进行 `vermagic` 一致性检查，不匹配则不会发布软件源。

## 目录结构

```text
.github/workflows/   GitHub Actions 构建与发布工作流
Config/              通用配置、平台配置及软件包清单
Scripts/             软件源收集、软件包处理及固件设置脚本
```

## License

[MIT License](LICENSE)
