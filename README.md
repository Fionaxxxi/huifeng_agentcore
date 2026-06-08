# huifeng_agentcore

Agent 层开发仓库。

## 项目结构

```
huifeng_agentcore/
│
├── src/                          # 源代码
│   ├── types.py                  # Pydantic 数据模型
│   ├── config.py                 # 配置加载
│   ├── exceptions.py             # 自定义异常
│   ├── utils.py                  # trace_id、日志工具
│   ├── retriever.py              # 检索工具调用
│   ├── prompt_builder.py         # Prompt 组装器
│   ├── llm_engine.py             # LLM 推理引擎
│   └── main.py                   # Agent 主流程编排
│
├── tests/                        # 测试
│   ├── test_retriever.py
│   ├── test_prompt_builder.py
│   ├── test_llm_engine.py
│   └── test_main.py
│
└── mock/                         # Mock 数据
    └── mock_retriever.py
```

## 文件说明

| 文件 | 功能 | 对应需求点 |
|------|------|-----------|
| `types.py` | 统一数据模型（AgentRequest/Response） | 参数校验 |
| `config.py` | 加载 .env 配置 | 环境配置 |
| `exceptions.py` | 自定义异常类 | 异常处理 |
| `utils.py` | trace_id 生成、日志格式化 | 基础日志 |
| `retriever.py` | 调用检索工具，获取文档块 | 功能点 2.2 |
| `prompt_builder.py` | 组装 System Prompt + 检索上下文 | 功能点 2.3 |
| `llm_engine.py` | 调用 LLM 生成答案 | 功能点 2.4 |
| `main.py` | 主流程编排，串联检索→组装→生成 | 功能点 2.1/2.5/2.6/2.7 |
| `mock/mock_retriever.py` | 假检索数据，独立开发用 | 开发辅助 |
