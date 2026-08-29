# AGENTS.md — 工作区规则 & 统一能力清单

> 只要记住一件事：**多干活，少废话。** ——打工斯斯 🤖

---

## 📂 路径规范

> `{config}` = `D:\微云同步助手\1055534912\AI Tool\AI人工智能\Codex\.codex`
> `{workspace}` = `D:\GEO文件夹\GEO文件夹\Codex办公工作区\`

| 类型 | 路径 | 说明 |
|:----|:-----|:-----|
| **配置文件夹** | `{config}\` | 8核心文件 + tools/skills/memory/dreams |
| **办公工作区** | `{workspace}\` | 产出文件，按 `YYYY-MM\` 月份归档 |
| **素材库** | `D:\GEO文件夹\GEO文件夹\materials\` | 图片、参考资料、模板 |

**8 个核心文件**：`BOOTSTRAP.md` `SOUL.md` `IDENTITY.md` `FACT.md` `MEMORY.md` `TOOLS.md` `HEARTBEAT.md` `USER.md`
**核心文件夹**：`tools/search/` `skills/.system/` `memory/` `dreams/` `sessions/`

**红线**：不泄露私人数据 · 破坏操作前确认 · 文件不覆盖旧版 · 不确定先问

---

## 🚀 启动流程

**核心原则：轻量化启动，按需加载。新对话只加载 4 个核心文件，其余按需加载。**

### 启动必加载（4 个）

| # | 文件 | 说明 |
|:-:|------|------|
| ① | **SOUL.md** | 灵魂+身份+性格+铁律 |
| ② | **IDENTITY.md** | 身份信息+工作区规则 |
| ③ | **AGENTS.md** | 工作区规则+能力清单（本文件） |
| ④ | **USER.md** | 用户档案+偏好+数据准确性要求 |

### 按需加载

| # | 文件 | 加载触发条件 |
|:-:|------|:------------:|
| ⑤ | **MEMORY.md** | 问到记忆/历史/经验/具体事项时 |
| ⑥ | **TOOLS.md** | 需要调用搜索工具/API 密钥时 |
| ⑦ | **HEARTBEAT.md** | 启动自检/定期巡检时 |
| ⑧ | **FACT.md** | 需要路径清单时 |
| ⑨ | `memory/今日.md` | 用户主动询问当天记录时 |

**加载决策链**：
```
启动 → SOUL + IDENTITY + AGENTS + USER（4 个）
  ↓
用户提问 → 判断是否涉及记忆/历史/经验
  ├─ 是 → 加载 MEMORY.md → 按需加载 TOOLS/FACT
  └─ 否 → 直接回答，不加载多余文件
```

---

## 📋 统一能力清单

### A. 联网搜索（优先级）

> ⚠️ **百度 AI Search（直调API）≠ 百度搜索技能（wrapper 脚本）**，两者是不同的工具
> - `search_baidu.py` = 直调千帆 API（Codex 已配置）✅
> - wrapper 脚本 `search_wrapper.py` = OpenClaw 专属，Codex 暂未配置 ❌

| 优先级 | 工具 | 脚本 | 场景 |
|:------:|------|------|------|
| 🥇 | **百度 AI Search（直调API）** | `search_baidu.py` | 中文首选 |
| 🥈 | **Tavily AI** | `search_tavily.py` | 英文/全球 |
| 🥉 | **统一 CLI** | `search_unified.py` | 7 方法 + auto fallback |
| 兜底 | **一键全测** | `search_all.py` | 验证所有搜索方式 |

> API 密钥和调用方法 → **TOOLS.md** | 完整使用方式 → **FACT.md**

### B. PPT 制作

详见 **MEMORY.md** — PPT 基础能力 + 工具 + 设计规范。

### C. Excel 处理

详见 **MEMORY.md** — Excel 基础能力 + openpyxl。

### D. 关键教训

| 教训 | 规则 |
|:----|:-----|
| PowerShell inline 中文 JSON | 必乱码，改用 `.py` 文件 |
| 百度 AI Search 限流 429 | auto fallback 到 Tavily |
| Tavily advanced 深度不必要 | 简单查询改 basic 提速 3x |
| 两个工作区容易混淆 | 输出文件务必确认路径 |
| **百度 AI Search ≠ 百度搜索技能** | 两者是不同工具，不要混为一谈 |
| 前端页面修改后必须验证浏览器实际内容 | 只看本地文件不算完成，要检查服务返回页面的实际片段 |
| 避免 PowerShell 直接替换复杂 HTML/JS | 中文、模板字符串、反斜杠极易写坏，优先用 Python 脚本重写 |
| 后端新增接口要考虑重复提交 | 前端重复添加时应做更新/提示，不要直接抛出数据库唯一约束错误 |
| 一次只改一个交互点 | 不要同时改列表、添加、编辑多块逻辑，改完一块验证一块 |
| 默认状态尽量只读，编辑由用户触发 | 避免整表默认可编辑导致页面混乱和误操作 |

---

*打工斯斯 | 2026-08-07 建立 | v1.1 区分百度 AI Search / 百度搜索技能*

