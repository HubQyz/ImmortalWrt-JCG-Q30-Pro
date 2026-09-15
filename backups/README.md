# 路由器备份文件 (JCG Q30 Pro)

本目录用于存放 JCG Q30 Pro 的各类备份文件，方便刷机失败时恢复。

## 📁 文件说明

| 文件名 | 类型 | 说明 | 校验值 (SHA256) |
|---|---|---|---|
| `jcg-q30-pro-stock-full.bin` | 原厂完整固件 | 编程器/全片备份 | 待补充 |
| `jcg-q30-pro-stock-uboot.bin` | 原厂 U-Boot | bootloader 备份 | 待补充 |
| `jcg-q30-pro-partitions.txt` | 分区表 | mtd 分区信息 | 待补充 |
| `openwrt-config-backup.tar.gz` | 配置备份 | LuCI 系统→备份/恢复 生成 | 待补充 |

## ⚠️ 注意事项

1. **文件大小限制**：GitHub 单文件限制 100MB，仓库建议总大小 1GB 以内。
   如果完整固件超过 100MB，请勿直接提交，改用网盘或 Git LFS。
2. **备份来源**：所有备份均从本人设备提取，仅供本人恢复使用。
3. **校验方法**：
   ```bash
   sha256sum 文件名
