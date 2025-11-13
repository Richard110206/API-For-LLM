## 面向大语言模型的 API

![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)
![FastAPI](https://img.shields.io/badge/FastAPI-0.104.1-green.svg)
![Ollama](https://img.shields.io/badge/Ollama-LocalLLM-orange.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

[中文版本](README_zh-CN.md) | [English Version](README.md)

这是一个轻量级 Python API 服务，可连接至本地大语言模型（LLM）Ollama，同时支持 API 密钥验证与额度管理功能。

### 项目概述
本项目基于 FastAPI 提供接口，用于与本地 Ollama 大语言模型交互。它实现了 API 密钥认证、调用额度限制、直接生成大语言模型响应等核心功能，能让用户安全、可控地使用本地大语言模型的能力。

### 🚀 功能特性
- **API 密钥验证**：仅允许持有有效 API 密钥的授权用户访问大语言模型服务。
- **额度管理**：每个 API 密钥都有初始调用额度限制，用于控制服务使用量。
- **简单集成**：提供易于使用的 HTTP POST 接口，可发送提示词并接收大语言模型的响应。
- **本地部署**：支持与本地部署的 Ollama 模型（如 Mistral）配合使用，无需依赖外部 API。
  
### 📌 前置条件
- Python 环境：需安装 Python 3.8 及以上版本。
- Ollama 安装：
从官方网站下载安装 Ollama，或使用以下命令安装：
```bash
brew install ollama
```
在本地拉取所需的大语言模型（默认模型为 Mistral）：
```bash
ollama run mistral
```

### 📝 安装步骤

**1. 克隆仓库**
```bash
git clone https://github.com/Richard110206/API-For-LLM.git
cd API-For-LLM
```

**2. 安装依赖**

通过 `requirements.txt` 文件安装所有必需的 Python 包：
```bash
pip install -r requirements.txt
```

### 🔧 快速开始
**1. 启动 API 服务**
使用 Uvicorn 运行 FastAPI 服务：
```bash
uvicorn main:app --reload
```
服务将在 `http://127.0.0.1:8000` 地址启动。开发阶段可使用 `--reload` 参数实现自动重载（生产环境需移除该参数）。

**2. 测试 API**
- 方式 1：使用内置测试脚本
执行预先编写的测试脚本，快速验证 API 功能：
```bash
python test_api.py
```
该脚本会向 API 发送一个提示词（默认提示词为 “告诉我什么是大语言模型？”，你也可以根据需求修改），并打印大语言模型返回的响应。

- 方式 2：使用 Postman 或 Curl 等工具

  - 请求方法：POST
  - 请求地址：`http://127.0.0.1:8000/generate?prompt=你的提示词`
  - 请求头：x-api-key：你的 API 密钥（从 .env 文件中获取）
  - Content-Type：application/json
<img width="564" height="711" alt="image" src="https://github.com/user-attachments/assets/096b2cf8-d7c1-4a2b-930c-13802a90a22a" />

**3. 查看 API 文档**

FastAPI 会自动生成交互式文档：Swagger UI：在浏览器中访问 `http://127.0.0.1:8000/docs`

### 参考资料

[15 分钟学会 Ollama - 免费在本地运行大语言模型](https://www.youtube.com/watch?v=UtSSMs6ObqY&t=600s)

[如何用 Python 构建 API（集成大语言模型、FastAPI、Ollama 等）](https://www.youtube.com/watch?v=cy6EAp4iNN4)
