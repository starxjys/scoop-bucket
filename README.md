# scoop-bucket

[![Tests](https://github.com/starxjys/scoop-bucket/actions/workflows/ci.yml/badge.svg)](https://github.com/starxjys/scoop-bucket/actions/workflows/ci.yml)
[![Excavator](https://github.com/starxjys/scoop-bucket/actions/workflows/excavator.yml/badge.svg)](https://github.com/starxjys/scoop-bucket/actions/workflows/excavator.yml)

个人自用的 [Scoop](https://scoop.sh) 软件仓库（bucket），基于官方
[ScoopInstaller/BucketTemplate](https://github.com/ScoopInstaller/BucketTemplate) 维护。
仓库添加 `scoop-bucket` topic 后可被 [scoop.sh](https://scoop.sh) 索引收录。

## 仓库中的软件

| 软件 | manifest | 说明 | 自动更新 |
| --- | --- | --- | --- |
| ikuai-cli | [ikuai-cli.json](bucket/ikuai-cli.json) | 爱快路由器命令行工具（网络/VPN/防火墙等） | ✅ checkver + autoupdate |
| Firewall App Blocker | [fab.json](bucket/fab.json) | 易于使用的 Windows 防火墙工具 | ✅ checkver + autoupdate |
| 小丸工具箱 | [xiaowan.json](bucket/xiaowan.json) | 音视频处理工具（x264/ffmpeg 图形界面） | ❌ 静态版本（官网无版本信息源） |
| Herdr | [Herdr.json](bucket/Herdr.json) | 终端工作区管理器（AI 编码 agent 用，Windows 预览版） | ✅ checkver + autoupdate |

## 安装

```pwsh
scoop bucket add starxjys https://github.com/starxjys/scoop-bucket
scoop install starxjys/ikuai-cli
```

## 添加新 manifest

复制 `bucket/app-name.json.template` 为 `bucket/<app-name>.json`，按
[App Manifests](https://github.com/ScoopInstaller/Scoop/wiki/App-Manifests) 规范填写，
提交并推送即可。仓库内置 [Excavator](.github/workflows/excavator.yml) 每 4 小时自动
检查各 manifest 的上游新版本并更新版本号、下载地址与校验和（需要仓库 Actions 权限为
"Read and write"）。

## 贡献 manifest

请参考 [Contributing Guide](https://github.com/ScoopInstaller/.github/blob/main/.github/CONTRIBUTING.md)。
