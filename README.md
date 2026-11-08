# clash-config

mihomo / OpenClash 多机场聚合配置模板。

- 25 个策略组（主控 + 港日韩新美地区三件套 + 业务 + 开关）
- 全量分流（123 条规则 / 34 个规则集）
- 零 DNS 泄露（fake-ip + respect-rules + TUN strict-route + 关闭 IPv6）
- Steam 下载直连、AI 遥测拦截

## 文件说明

| 文件 | 用途 |
|---|---|
| `config.yaml` | mihomo 完整配置（多机场聚合，直接导入） |
| `merge-single.yaml` | Clash Verge Rev 覆写 · 单订阅通用版 |
| `merge-multi.yaml` | Clash Verge Rev 覆写 · 多机场 Provider 版 |
| `openclash-overwrite.ini` | OpenClash 覆写模块（v0.46+） |
| `openclash-overwrite.txt` / `.conf` | 同上，备用扩展名 |

## 拉取链接（OpenClash 覆写模块）

重装 OpenClash 后，在「运行状态 → 覆写模块 → 添加新模块 → 远程模块」填入以下 URL，即可自动拉取，无需手动上传文件：

```
https://raw.githubusercontent.com/GA-LSQ/clash-config/main/openclash-overwrite.ini
```

> 说明：
> - 远程模块方式需要 OpenClash 能访问 raw.githubusercontent.com（国内可能需先走代理）。
> - 若拉取失败，也可以手动下载 `openclash-overwrite.ini` 后走「本地模块」上传。
> - 拉取后仍需：打开模块启用开关 → 确认 `config = all` → 内核选 Meta/Mihomo → 运行模式选 Fake-IP → 重启插件。

## 使用前必改

`config.yaml` 和 `merge-multi.yaml` 里的订阅链接是占位符，替换成你自己的机场订阅：

```yaml
proxy-providers:
  airport1:
    url: "https://你的机场1订阅链接&flag=clash"
```

## 隐私

本仓库为私有仓库。若改公开，请务必先清除真实订阅链接。
