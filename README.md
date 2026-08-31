# dingclaw

dingclaw 是以本人身份回复、默认 fail-closed 的钉钉数字分身运行时。

## 安装

```bash
pipx install 'dingclaw==0.4.5'
dingclawd --version
```

PyPI：<https://pypi.org/project/dingclaw/0.4.5/>

## 下载与源码

wheel、无 Git 信息的 sdist 源码包及 SHA-256 校验文件见 [v0.4.5 Release](https://github.com/adongguo/dingclaw/releases/tag/v0.4.5)。

本仓库用于公开发行。GitHub 自动生成的 Source code 压缩包只包含发行元数据；完整对应源码请使用 Release 中的 `dingclaw-0.4.5.tar.gz`。

## 校验

```bash
shasum -a 256 -c dingclaw-0.4.5-py3-none-any.whl.sha256
shasum -a 256 -c dingclaw-0.4.5.tar.gz.sha256
```

## 许可证

`0.4.5` 及后续新版本使用 `GPL-3.0-or-later`；此前已发布版本继续适用其随版本提供的许可证。详见 [LICENSE](LICENSE)。
