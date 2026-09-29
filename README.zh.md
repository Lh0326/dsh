# DeepSeek Harness

[English](README.md) | 中文

> **本仓库是 Lh0326 维护的 [deepseek-ai/deepseek-harness](https://github.com/deepseek-ai/deepseek-harness) Fork。** 可从这里获取源码，学习和扩展上游框架。相关项目 [dsh-pet-desktop](https://github.com/Lh0326/dsh-pet-desktop) 在独立仓库中提供桌面宠物交互界面。

DeepSeek Harness（`dsh`）是由 [DeepSeek AI](https://deepseek.com) 开发的开源 agent harness（智能体框架）。

它采用**一切皆插件**的架构，并由 [Cordis](https://github.com/cordiverse/cordis) 驱动，其设计参见论文 [_A Programming Paradigm for Spatiotemporal Composability_](https://github.com/cordiverse/paper)。

## 可以从这里探索什么

- **运行 agent：** 通过 Web UI 或 headless 配置处理项目文件、命令、计划与委派任务。
- **组合能力：** 通过 Cordis 插件和配置组合模型提供方、工具、权限与会话服务。
- **开发集成：** 使用 TypeScript 或 Python SDK，或基于已有扩展点开发插件。

这些能力来自上游项目。下文分别说明本 Fork 的源码运行方式与上游 npm 发布包的体验方式。

## 开发者预览

DeepSeek Harness 目前处于 _开发者预览_ 阶段，正在快速迭代。**未来将出现破坏兼容性的变更。**

## 运行

### 通过 `npm` 运行

准备 Node.js 22.x 中的 22.19+ 版本，或 Node.js 24+，然后运行上游发布包：

```sh
npx @deepseek-ai/dsh web
```

该命令会启动 Web UI，默认地址为 `http://127.0.0.1:3080`。打开 **Settings → Models** 配置模型提供方，选择工作区后再发送任务。详见 [Web UI 指南](docs/user/guide/index.md)。

### 从源码运行

运行本 Fork 需要满足相同的 Node.js 要求，并使用 [package.json](package.json) 固定的 `pnpm@11.7.0`。安装与构建需要网络连接，执行模型任务需要配置模型提供方。

```sh
git clone https://github.com/Lh0326/dsh.git
cd dsh
pnpm install --frozen-lockfile
pnpm run build
pnpm dsh web
```

服务启动后会打印访问地址。其他启动模式和参数见 [CLI 参考](apps/cli/README.md)。如遇安装问题，先核对运行时版本与[开发指南](docs/development.md)，再考虑调整锁文件。

## 源码阅读地图

| 从这里开始 | 内容 |
|---|---|
| [架构设计](docs/architecture.md) | 插件组合、agent loop（智能体循环）与扩展点 |
| [包分组](packages/README.md) | 各类能力在包之间的分工 |
| [可运行示例](examples/README.md) | 示例配置与应用入口 |
| [插件开发](docs/user/develop/basic/) | 创建并组合自己的插件 |
| [TypeScript SDK](packages/sdk/README.md) / [Python SDK](python/README.md) | 将框架集成到其他应用 |

## 社区与支持

- 欢迎通过 [GitHub Discussions](https://github.com/deepseek-ai/deepseek-harness/discussions) 提交反馈或 bug 报告。
- 为你的插件仓库添加 [`dsh-plugin`](https://github.com/topics/dsh-plugin) 话题，便于被发现。
- 欢迎加入 DeepSeek Harness 企微群：扫码添加企微小助手并填写入群问卷，完成后小助手会邀请你入群。

<table>
  <thead>
    <tr>
      <th align="center">企微小助手</th>
      <th align="center">入群问卷</th>
      <th align="center">微信公众号</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center"><img src="assets/community-wecom-assistant.png" alt="DeepSeek Harness 企微小助手二维码" width="180" height="180"></td>
      <td align="center"><a href="https://trtgsjkv6r.feishu.cn/share/base/form/shrcnIt5twSVdLGD52KJBckGCgg"><img src="assets/community-wecom-survey.png" alt="DeepSeek Harness 入群问卷二维码" width="180" height="180"></a></td>
      <td align="center"><img src="assets/community-wechat-official-account.png" alt="DeepSeek Harness 团队微信公众号二维码" width="180" height="180"></td>
    </tr>
  </tbody>
</table>

## 参与贡献

参见 [CONTRIBUTING.md](CONTRIBUTING.md)。

## 开发

请先阅读[开发指南](docs/development.md)与[架构文档](docs/architecture.md)。

面向 agent：请遵循 [AGENTS.md](AGENTS.md)。

## 许可证

[MIT](LICENSE)

第三方依赖及其许可证见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。
