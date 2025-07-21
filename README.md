# ZHIPU AI 开发者文档

智谱 AI 平台开发者文档的源代码仓库，基于 Mintlify 构建的现代化文档站点。

## 🚀 快速开始

### 环境要求

- Node.js 16.0 或更高版本
- npm 或 yarn 包管理器

### 本地开发

1. **安装 Mintlify CLI**
   ```bash
   npm i -g mint
   ```

2. **克隆项目**
   ```bash
   git clone <repository-url>
   cd devbook
   ```

3. **启动开发服务器**
   ```bash
   mint dev
   ```
   
   服务器将在 `http://localhost:3000` 启动，支持热重载。

4. **OPENAPI定义校验**

> OPEN API 接口的定义基于 OPENAPI 3.0.1 规范，在 `openapi/openapi.json` 文件中定义。

  校验 `openapi.json` 是否符合 OPENAPI 3.0.1 规范
   ```bash
   mint openapi-check openapi/openapi.json
   ```

5. **断链校验**
   ```bash
   mint broken-links
   ```

**[`OEPNAPI`接口定义](openapi/openapi.json) 推荐使用 https://editor.swagger.io/ 在线编辑，或使用 Webstorm 本地编辑可视化**

## 项目结构

```
devbook/
├── cn/ # 中文文档
│ ├── api/ # API 文档
│ │ ├── agents/ # 智能体相关
│ │ ├── audio/ # 音频相关
│ │ ├── chat/ # 聊天对话相关
│ │ ├── embedding/ # 文本嵌入相关
│ │ ├── file/ # 文件管理相关
│ │ ├── image/ # 图像生成相关
│ │ ├── tools/ # 工具相关
│ │ └── video/ # 视频生成相关
│ ├── guide/ # 使用指南
│ ├── issue/ # 常见问题
│ └── update/ # 更新日志
├── en/ # 英文文档
│ ├── api/ # API 文档
│ │ ├── agents/ # 智能体相关
│ │ ├── audio/ # 音频相关
│ │ ├── chat/ # 聊天对话相关
│ │ ├── embedding/ # 文本嵌入相关
│ │ ├── file/ # 文件管理相关
│ │ ├── image/ # 图像生成相关
│ │ ├── tools/ # 工具相关
│ │ └── video/ # 视频生成相关
│ ├── guide/ # 使用指南
│ ├── issue/ # 常见问题
│ └── update/ # 更新日志
├── openapi/ # OpenAPI 规范文件
│ └── openapi.json # 完整的 OpenAPI 规范（主入口，已模块化合并）
├── resource/ # 静态资源
│ ├── favicon.svg
│ ├── logo_icon.png
│ └── logo.png
├── style.css # 样式文件
├── docs.json # 文档配置
├── LICENSE # 许可证
├── CONTRIBUTING.md # 贡献指南
└── CODE_OF_CONDUCT.md # 行为准则
```

## OpenAPI 规范文件

项目采用模块化设计，但当前仅保留合并后的主入口文件 `openapi/openapi.json`，该文件包含所有 API 的完整 OpenAPI 3.0.1 规范定义。

### 主要 API 模块与路径

- **聊天对话 API**
  - `/paas/v4/chat/completions` - 聊天补全

- **文本嵌入 API**
  - `/paas/v4/embeddings` - 文本嵌入

- **音频处理 API**
  - `/paas/v4/audio/speech` - 文本转语音
  - `/paas/v4/audio/transcriptions` - 语音转文本
  - `/paas/v4/audio/customization` - 语音定制

- **图像生成 API**
  - `/paas/v4/images/generations` - 图像生成

- **视频生成 API**
  - `/paas/v4/videos/generations` - 视频生成
  - `/paas/v4/async-result/{id}` - 异步结果查询

- **文件管理 API**
  - `/paas/v4/files` - 文件上传与列表
  - `/paas/v4/files/{file_id}` - 文件信息获取与删除
  - `/paas/v4/files/{file_id}/content` - 文件内容下载

- **工具 API**
  - `/paas/v4/web_search` - 网络搜索
  - `/paas/v4/tools` - 综合网络搜索

- **助手 API**
  - `/paas/v4/assistant` - 助手对话
  - `/paas/v4/assistant/list` - 查询助手支持能力
  - `/paas/v4/assistant/conversation/list` - 查询助手对话统计

- **批处理任务 API**
  - `/paas/v4/batches` - 创建与列出批处理任务
  - `/paas/v4/batches/{batch_id}` - 获取批处理任务详情
  - `/paas/v4/batches/{batch_id}/cancel` - 取消批处理任务

- **知识库 API**
  - `/knowledge` - 创建与获取知识库列表
  - `/knowledge/{id}` - 编辑、获取详情、删除知识库
  - `/knowledge/capacity` - 获取知识库使用量详情

- **知识库文档 API**
  - `/document/upload_document/{id}` - 向知识库上传文档

- **智能体（Agent）API**
  - `/v1/agents` - 智能体对话
  - `/v1/agents/async-result` - 查询智能体异步结果

> 详细字段、参数和响应格式请参考 [openapi/openapi.json](openapi/openapi.json) 文件或使用 Swagger 编辑器进行可视化浏览。

## 贡献指南

欢迎贡献代码和文档！请查看 [CONTRIBUTING.md](CONTRIBUTING.md) 了解详细的贡献流程。

## 许可证

本项目采用 MIT 许可证，详见 [LICENSE](LICENSE) 文件。

## 联系我们

- 官网：https://open.bigmodel.cn/
- 开发者社区：https://chat.z.ai/
- 邮箱：user_feedback@z.ai