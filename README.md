# dingclaw

dingclaw 是以本人身份在钉钉里代答、默认 fail-closed 的数字分身运行时：本机常驻，经钉钉官方 DWS CLI 收发消息，把该处理的消息交给 CLI Agent（Qoder CLI / Codex / Claude Code / pi），再以本人身份把结果发回去。每条消息带 AI 标识，发送总闸默认关闭。

## 安装

```bash
pipx install 'dingclaw==0.4.7'
dingclawd --version
```

PyPI：<https://pypi.org/project/dingclaw/0.4.7/>

## 主要能力

- 召唤即任务：本人 `@me <任务>`、同事单聊 `@你 <任务>`、群里真实 @ + 召唤词；一次召唤一张进度卡，支持补充、纠正和「停止」。
- 投递只认可核对的证据：`ACCEPTED` 不算送达，结果说不清就停下，只用同一个 UUID 幂等重试。
- 收件箱面板 `dingclawd tui`：分诊、全部会话、时间线、未读、找我的五个视图；手动回复，或选中消息让分身直接回复。
- 群告警统计与分级响应、独立健康巡检、轻量路由。

完整说明见 PyPI 页面。

## 下载与校验

[v0.4.7 Release](https://github.com/adongguo/dingclaw/releases/tag/v0.4.7) 附带 wheel、sdist 和 SHA-256 校验文件；交付手册、配置参考与健康巡检文档在 sdist 的 `docs/` 目录。

```bash
shasum -a 256 -c dingclaw-0.4.7-py3-none-any.whl.sha256
shasum -a 256 -c dingclaw-0.4.7.tar.gz.sha256
```

## 许可证

`0.4.5` 及后续新版本使用 `GPL-3.0-or-later`；此前已发布版本继续适用其随版本提供的许可证。详见 [LICENSE](LICENSE)。
