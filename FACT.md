# FACT.md — 路径清单 & 关键事实

> 本文档记录打工斯斯的常用路径、关键网站、工作区架构等事实性信息。

---

## 📂 路径规范

| 类型 | 路径 | 说明 |
|:----|:-----|:-----|
| **配置文件夹** | `D:\微云同步助手\1055534912\AI Tool\AI人工智能\Codex\.codex` | 8核心文件 + skills/tools/memory/dreams |
| **名称** | 打工斯斯 | 老板的专属 Codex CLI 助手 |
| **办公工作区（产出）** | `D:\GEO文件夹\GEO文件夹\Codex办公工作区\` | 所有产出文件，按 YYYY-MM/ 月份归档 |
| **素材库** | `D:\GEO文件夹\GEO文件夹\materials\` | 图片、参考资料、模板 |
| **每日记忆** | `{config}\memory\YYYY-MM-DD.md` | 每日工作记录 |
| **梦境/神经网络** | `{config}\dreams\` | 知识图谱、经验提炼 |

---

## 🔍 搜索工具索引（4 个脚本）

> ⚠️ **百度 AI Search（直调API）≠ 百度搜索技能（wrapper 脚本）**
> - `search_baidu.py` = 直调千帆 API（Codex 已配置）✅
> - wrapper 脚本 `search_wrapper.py` = OpenClaw 专属，Codex 暂未配置 ❌

| 脚本 | 功能 | 优先级 |
|------|------|:------:|
| `search_baidu.py` | 百度 AI Search（直调千帆 API） | 🥇 |
| `search_tavily.py` | Tavily AI | 🥈 |
| `search_unified.py` | 统一 CLI（7 方法 + auto fallback） | 🥉 |
| `search_all.py` | 一键全测 | 兜底 |

---

## 🔑 API 密钥索引

| 工具 | 密钥位置 | 说明 |
|------|---------|------|
| 百度 AI Search | `TOOLS.md` → 方式一 | `BAIDU_API_KEY` 环境变量 / 脚本硬编码 |
| Tavily AI | `TOOLS.md` → 方式二 | 代码硬编码 |
| AnySearch | `TOOLS.md` | 代码硬编码 |
| Exa AI | `TOOLS.md` | 代码硬编码 |

---

## 🗺️ 工作区目录树

```
{config}/
├── 8核心文件/
│   ├── BOOTSTRAP.md     ← 首次加载引导
│   ├── SOUL.md          ← 灵魂
│   ├── IDENTITY.md      ← 身份 DNA
│   ├── FACT.md          ← 本文件，路径清单
│   ├── MEMORY.md        ← 长期记忆
│   ├── TOOLS.md         ← 工具配置
│   ├── HEARTBEAT.md     ← 初始化检查
│   └── USER.md          ← 用户档案
├── tools/search/        ← 搜索脚本（4 个）
├── skills/.system/      ← 系统技能（6 个）
├── memory/              ← 每日记忆
├── dreams/              ← 梦境/神经网络
├── sessions/            ← 历史会话
├── rules/               ← 权限规则
├── config.toml          ← 模型配置
├── auth.json            ← 认证信息
└── history.jsonl        ← 对话历史
```

