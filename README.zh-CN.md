[简体中文](README.zh-CN.md) | [English](README.md)

# dsh-superagent

> **仅为研究原型，非 DeepSeek 官方产品。** 这份代码来自我们团队的日常开发工作，其中大量工程由编码 Agent 完成。请把它当作研究代码，而非可用于生产的软件：它可能仍有 Bug，编码风格与工程实践也可能不一致。在自己的环境中使用前，请先审查并自行调整。
>
> 我们已为公开而做了适配，它与内部版本以及《Exploring Super-agent Design: Towards a More Autonomous Agent System》一文所描述的实现并不完全相同。文中讨论的部分设计是未来开发方向，本原型尚未实现。

dsh-superagent 是面向单个 GitHub 仓库的主动式编码 Agent，以 [DeepSeek Harness](https://www.deepseek.com/en/harness/) 的 bundle 形式打包。它监听 GitHub，并可选监听 Feishu。当获允许的人向它提出请求时，它会开一个工单（Ticket），在自己的 Agent 会话和目录中独立完成工作，并回到发起请求的对话中作答，例如给出一个 Pull Request。Web 面板则展示哪些事项需要人来处理。

它同时也是一种与 Agent 协作的方式：**占用尽可能少的人力注意力，产出尽可能多的价值。** 一个能为整个团队干活的 Agent，也可能消耗整个团队的注意力，因此它只在被请求时、或团队明文规则允许时才行动；只在有人必须处理、或有人能直接使用结果时才发言。[docs/000-philosophy.md](docs/000-philosophy.md) 阐述了这一原则，以及它对运维者提出的要求。

## 安装部署

部署步骤较多，因此由 Agent 协助完成。请告诉你的编码 Agent：

> 阅读 SETUP.md，并和我一起完成 dsh-superagent 的安装配置。

它会一次只问一个简短的问题，先展示完整计划，然后完成全部安装和配置。[SETUP.md](SETUP.md) 就是它遵循的步骤。

## 文档

请按编号顺序阅读各文档；每一篇只依赖它之前的那些。

- [000 设计哲学](docs/000-philosophy.md)
- [001 领域模型](docs/001-domain.md)
- [002 授权](docs/002-authorization.md)
- [003 执行](docs/003-execution.md)
- [004 提示词](docs/004-prompts.md)
- [005 面板](docs/005-panel.md)
- [006 部署](docs/006-deployment.md)：手动部署、配置、升级与故障排查
- [007 架构](docs/007-architecture.md)
- [008 实践手册](docs/008-cookbook.md)：新增一个 Source

## 开发

`pnpm check` 会依次运行类型检查、测试和构建。

## 许可证

[MIT](LICENSE)
