# ImmortalWrt for JCG Q30 Pro (512M)

基于 [immortalwrt/immortalwrt](https://github.com/immortalwrt/immortalwrt) 官方 `v25.12.1` 稳定版源码，通过 GitHub Actions 云编译的 JCG Q30 Pro (512M) 固件。

[![Build ImmortalWrt JCG Q30 Pro (Official 25.12 Stable)](https://github.com/HubQyz/ImmortalWrt-JCG-Q30-Pro/actions/workflows/build.yml/badge.svg)](https://github.com/HubQyz/ImmortalWrt-JCG-Q30-Pro/actions/workflows/build.yml)

---

## 📋 固件信息

| 项目 | 说明 |
|---|---|
| 源码 | ImmortalWrt 官方 v25.12.1 稳定版 |
| 目标平台 | mediatek / filogic |
| 目标设备 | JCG Q30 Pro (MT7981 / NAND 512M) |
| 内核版本 | Linux 6.12 LTS |
| 无线驱动 | mt76 开源驱动 |
| 固件格式 | .itb (FIT image) |
| 包管理器 | apk (Alpine Package Keeper) |
| 默认地址 | 192.168.6.1 |
| 默认密码 | 无（留空） |

---

## ✨ 固件特性

- ✅ 官方 ImmortalWrt 25.12 稳定版，持续跟进上游更新
- ✅ 软件包管理器为 **apk**（不再是 opkg）
- ✅ 内核 6.12 LTS，长期支持
- ✅ IPv6 支持完善
- ✅ 科学上网：**HomeProxy**（官方自带，基于 Sing-box）
- ✅ DNS 优化：**MosDNS v5 (sbwml)** + **SmartDNS** 双重方案
- ✅ 广告拦截：**AdBlock-Fast**（高性能 DNS 级拦截，含 GNU 加速工具包）
- ✅ 主题美化：**KUCAT 酷猫** + **Argon**（支持深色/浅色模式）
- ✅ 应用过滤：**OpenAppFilter**（家长控制）
- ✅ 系统监控：**Bandix** + **nlbwmon** + **FlowLens**
- ✅ 虚拟组网：**ZeroTier** + **Tailscale**
- ✅ 内网穿透：**Lucky** + **DDNSTO**
- ✅ 限速流控：**SQM** + **EqosPlus**
- ✅ 定时任务：**TaskPlan**
- ✅ 定时重启：**AutoReboot**
- ✅ 微信推送：**WeChatPush**
- ✅ VPN：**WireGuard**
- ✅ 应用商店：**iStore**

---

## 📦 内置插件清单

### 主题
- luci-theme-kucat（KUCAT 酷猫主题）
- luci-app-kucat-config
- luci-theme-argon
- luci-app-argon-config

### 科学上网 / DNS
- luci-app-homeproxy
- luci-app-mosdns
- mosdns
- v2dat
- v2ray-geoip
- v2ray-geosite
- luci-app-smartdns
- smartdns

### 广告拦截
- adblock-fast
- luci-app-adblock-fast

### 网络工具
- luci-app-sqm
- luci-app-eqosplus
- luci-app-upnp
- luci-app-wol
- luci-app-netwizard
- luci-app-arpbind

### 监控 / 统计
- luci-app-bandix
- luci-app-nlbwmon
- luci-app-flowlens

### 虚拟组网 / 远程
- luci-app-zerotier
- luci-app-tailscale-community
- luci-app-lucky
- luci-app-ddnsto

### 应用过滤 / 家长控制
- luci-app-oaf

### 系统工具
- luci-app-ttyd
- luci-app-taskplan
- luci-app-autoreboot
- luci-app-store
- luci-app-wechatpush

### VPN
- luci-app-wireguard

---

## 🚀 刷机须知

1. **U-Boot 要求**：建议使用支持 `.itb` 格式的 U-Boot（如 hanwckf/bl-mt798x 20241115+）
2. **首次刷机**：使用 `initramfs-recovery.itb` 过渡，再刷 `sysupgrade.itb`
3. **升级固件**：使用 `sysupgrade.itb`，建议 **不保留配置** 升级
4. **默认地址**：`192.168.6.1`
5. **默认密码**：无（留空）
6. **Wi-Fi**：请刷机后在后台查看或自行设置
7. **包管理器**：25.12 使用 **apk**，不再是 opkg
8. **U-Boot 文件**：Release 附件中的 `bl2-mt7981_jcg_q30_SP2_img` 和 `fip-mt7981_jcg_q30_SP2.bin` 来自 [Yuzhii0718/bl-mt798x-dhcpd](https://github.com/Yuzhii0718/bl-mt798x-dhcpd)

---

## 💾 备份文件

本仓库 `backups/` 目录存放了刷机前的关键分区备份：

- `backup_mt7981-jcg_q30_mtd_bl2_bl2_0x0-0x100000_20260813.bin` — BL2 一级引导
- `backup_mt7981-jcg_q30_mtd_Factory_Factory_0x0-0x200000_20260813.bin` — 出厂数据（含 MAC / 无线校准）
- `backup_mt7981-jcg_q30_mtd_fip_fip_0x0-0x200000_20260813.bin` — FIP 二级引导（含 U-Boot）

详见 [backups/README.md](./backups/README.md)

---

## ⚠️ 免责声明

- 本固件仅供学习交流使用，请勿用于商业用途。
- 刷机有风险，操作需谨慎。因刷机造成的设备损坏、数据丢失等后果，作者不承担任何责任。
- 请在充分了解刷机流程后再进行操作，建议提前备份原厂固件和 U-Boot。

---

## 🔄 自动编译说明

- **手动触发**：在 GitHub Actions 页面选择 `Build ImmortalWrt JCG Q30 Pro (Official 25.12 Stable)`，点击 `Run workflow`。
- **定时触发**：每周六北京时间 02:38 自动检测上游更新，有更新则自动编译并发布 Release。
- **指纹机制**：任意一个上游仓库或第三方插件仓库有更新，都会触发重新编译。
- **Release 保留策略**：仅保留最近 3 个 Release，旧的会自动清理。

---

## 📝 目录结构
