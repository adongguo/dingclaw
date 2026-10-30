# dingclaw

dingclaw 是以本人身份在钉钉里代答、默认 fail-closed 的数字分身运行时：本机常驻，经钉钉官方 DWS CLI 收发消息，把该处理的消息交给 CLI Agent（Qoder CLI、千问办公、Codex、Claude Code、pi），再以本人身份把结果发回去。每条消息带 AI 标识，发送总闸默认关闭。

## 安装

Python 包（macOS，Python 3.10 及以上）：

```bash
pipx install 'dingclaw==0.14.2'
dingclawd --version
```

PyPI：<https://pypi.org/project/dingclaw/0.14.2/>

macOS App（Apple Silicon，macOS 26 及以上）：在 [v0.14.2 Release](https://github.com/adongguo/dingclaw/releases/tag/v0.14.2) 下载 `Dingclaw-0.14.2-macos-arm64.zip`，解压后把 `Dingclaw.app` 放进「应用程序」。App 经 Developer ID 签名并通过 Apple 公证，内置 Python 运行时和同版本的 wheel，首次启动按引导安装内核。从旧版本升级时，App 与内核要换成同一个版本；手机分身开着时，只换 App 或只换内核都会让手机连不上 Mac，换完 App 要按新 App 的引导重新完成手机配对。

## 主要能力

- 召唤即任务：本人 `@me <任务>`、同事单聊 `@你 <任务>`、群里真实 @ + 召唤词；一次召唤一张进度卡，支持补充、纠正和「停止」。本人经 DWS 或面板发出的消息不再触发召唤，交给分身请用分身按钮。
- 本地网关：`dingclawd run` 是本机唯一的钉钉数据出口，终端面板 `dingclawd tui` 和 Mac App 都经它读写。
- 多组织：服务多个组织时，统一收件箱按组织筛选，待办、审批、通讯录、告警群与案件按组织，每个组织有自己的自动回复开关、时段、召唤词与人员名单；会话列表一行一条，其他组织的会话带组织色点。
- Mac App：消息、群与公告、通讯录、DING、日程、待办、审批、分身控制台与运维诊断。
- 待回应：收尾话自动折叠进「可能无需回复」，`e` 处理一行、「全部处理」一次清掉整张列表；`R` 在任何视图都只清钉钉红点。
- 资料卡：Mac 与 iPhone 点头像看企业、部门、职位与直属主管，直接发消息、发 DING 或拉群。
- 多选拷贝：标记或扫选任意多条消息，一次拷成带发送人与时间的聊天记录文本，图片随文本一起进剪贴板。
- 回复 provider 可在 Qoder 与千问办公之间热切换；zclaude 运行时按固定版本与三重 sha256 校验安装，tarball 地址由部署方在配置里提供。
- 投递只认可核对的证据：`ACCEPTED` 不算送达，结果说不清就停下，只用同一个 UUID 幂等重试。

完整说明见 PyPI 页面；交付手册、配置参考与健康巡检文档在 sdist 的 `docs/` 目录。

## 下载与校验

Release 附带 wheel、sdist、Mac App 与各自的 SHA-256 校验文件：

```bash
shasum -a 256 -c dingclaw-0.14.2-py3-none-any.whl.sha256
shasum -a 256 -c dingclaw-0.14.2.tar.gz.sha256
shasum -a 256 -c Dingclaw-0.14.2-macos-arm64.zip.sha256
```

## 许可证

`0.4.5` 及后续新版本使用 `GPL-3.0-or-later`；此前已发布版本继续适用其随版本提供的许可证。详见 [LICENSE](LICENSE)。
