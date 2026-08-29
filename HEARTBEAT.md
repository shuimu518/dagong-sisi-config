# HEARTBEAT.md — 初始化检查清单

> 原则：直接 → 简洁 → 结果。跳过寒暄。

---

## 🚀 启动检查项（12项，3分钟内）

| # | 检查项 | 预算 | 验证标准 |
|:-:|--------|:----:|----------|
| ① | **配置文件自检** | <30s | 8核心文件可读，身份对齐 |
| ② | **搜索工具盘点** | <30s | 4个搜索脚本可用（百度/Tavily/Exa/AnySearch） |
| ③ | **根目录清理** | <30s | 仅留核心文件+5个核心文件夹 |
| ④ | **路径确认** | <20s | 配置文件夹 + 办公工作区路径正确 |
| ⑤ | **记忆加载** | <20s | memory/ 今日文件可读 |
| ⑥ | **梦境检查** | <10s | dreams/ 目录状态 |
| ⑦ | **认证验证** | <10s | auth.json 可读 |
| ⑧ | **模型配置确认** | <10s | config.toml 读取正常 |
| ⑨ | **高效回复** | 持续 | 跳过寒暄，先结论 |
| ⑩ | **文件归档** | <20s | 非核心→对应文件夹 |
| ⑪ | **诚信自检** | <10s | 红线检查，角色对齐 |
| ⑫ | **web_search权限** | <10s | 工具在default.rules中已配置 |

---

### 🔍 根目录清理标准

**保护列表（不动）：**
- **8核心文件**: `SOUL.md` `IDENTITY.md` `AGENTS.md` `USER.md` `MEMORY.md` `TOOLS.md` `HEARTBEAT.md` `FACT.md`
- **5核心文件夹**: `memory/` `skills/` `tools/` `dreams/` `sessions/`
- **系统文件夹**: `.sandbox/` `.sandbox-bin/` `.tmp/` `tmp/`

**清理规则：**
- 临时脚本 → `tmp/`
- 日志文件 → `.sandbox/`
- 旧版本备份 → `backups/`
- 会话记录 → `sessions/`

---

### 🧠 启动决策链

```
启动 → 读取 8 核心文件（SOUL + IDENTITY + AGENTS + USER + MEMORY + TOOLS + HEARTBEAT + FACT）
  ↓
用户提问 → 判断是否涉及记忆/历史/经验
  ├─ 是 → 读取 MEMORY.md → 按需读取 TOOLS/FACT
  └─ 否 → 直接回答，不加载多余文件
```

---

### 🔧 技术铁律

> **PowerShell 中文编码必乱码** → 所有含中文脚本写文件执行
>
> 标准流程：
> 1. 写 `.py` 脚本
> 2. `python xxx.py > D:\tmp\out.txt 2>&1`
> 3. `type D:\tmp\out.txt`

---

*打工斯斯 | 2026-08-10 | v2.0 更新（参考OpenClaw学习）*
