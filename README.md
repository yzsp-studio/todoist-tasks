<div align="center">

# 🎬 todoist-tasks

## 47 个 Todoist 操作全接通，动数据前先问你一句
## 47 Todoist actions wired in, and it still asks before changing anything

📮 **商务合作 / Business：wow.vip@foxmail.com**
🎬 **抖音 / Douyin：[v.douyin.com/07EjIDGVErY](https://v.douyin.com/07EjIDGVErY/)**

</div>

---

## 🇨🇳 中文

这是一个把自然语言请求接到 Todoist 的连接器技能：任务、项目、分区、评论、提醒、标签、过滤器、工作区与活动日志全部走已验证的实时调用，不凭空编造任务或 ID。它按「最窄的那个可用操作」路由，写入前必须拿到你的明确确认，并原样保留返回的 ID、状态、分页、日期与重复规则。除日常增删改查外，还能拉完成情况、逾期任务、karma 与连续打卡、项目健康度、工作区洞察，以及项目模板的导出与导入。连接器不可用、配额、授权、超时或结果只回来一部分时，它如实报告失败，绝不把空结果或报错包装成事实答案。

### ✨ 能做什么

- 一句话说清要做什么 → 自动落到最窄的那个 Todoist 操作，ID 绝不靠猜
- 任务、项目、分区、评论、提醒、标签、过滤器、工作区全链路可查可改
- 查已完成、查逾期、按日期范围取任务，分页与数据窗口如实说明
- karma、连续打卡、生产力统计、项目健康度与工作区洞察一次拿到
- 项目模板导出为 CSV 或分享链接，再导入现有项目补齐任务、分区和评论
- 批量改派带原子回滚；创建、完成、删除、导入前一律先要你确认

### 📦 包含的技能

- `todoist-tasks` —— 见 [`todoist-tasks/SKILL.md`](todoist-tasks/SKILL.md)

### 🚀 安装

```bash
git clone https://github.com/yzsp-studio/todoist-tasks.git
cp -r todoist-tasks/* "$DSH_HOME/skills/"
```

> 技能是**纯文本说明**（`SKILL.md` + `references/`），零依赖、零 API key，用你当前 agent 的会话额度。

---

## 🇬🇧 English

This skill wires natural-language requests to a live Todoist connector: tasks, projects, sections, comments, reminders, labels, filters, workspaces, and activity logs all go through verified callable operations, with no invented tasks or IDs. It routes each request to the narrowest available operation, requires explicit confirmation before any write, and preserves returned IDs, statuses, pagination, dates, and recurrence rules as-is. Beyond everyday create/update/complete work, it pulls completion history, overdue tasks, karma and streaks, project health, workspace insights, and project template export/import. When the connector is unavailable, or a call hits quota, authorization, timeout, or a partial result, it reports the failure honestly instead of dressing an empty or errored response up as a factual answer.

### ✨ What it does

- One plain-language request in, the narrowest Todoist operation out, with no guessed IDs
- Tasks, projects, sections, comments, reminders, labels, filters, and workspaces all readable and writable
- Completed tasks, overdue tasks, and date-range lookups, with pagination and data windows stated plainly
- Karma, goal streaks, productivity stats, project health, and workspace insights in one pass
- Export a project as template CSV or a shareable URL, then import it into an existing project
- Bulk assignment with atomic rollback; every create, complete, delete, or import asks for your go-ahead first

### 📦 Skills included

- `todoist-tasks` — [`todoist-tasks/SKILL.md`](todoist-tasks/SKILL.md)

### 🚀 Install

```bash
git clone https://github.com/yzsp-studio/todoist-tasks.git
cp -r todoist-tasks/* "$DSH_HOME/skills/"
```

> Skills are **plain-text instructions** (`SKILL.md` + `references/`). Zero dependencies, no API keys — they run on your agent's existing session quota.

---

## 📮 联系 / Contact

| | |
|---|---|
| 🎬 **抖音 / Douyin** | [https://v.douyin.com/07EjIDGVErY/](https://v.douyin.com/07EjIDGVErY/) |
| 📮 **商务合作 / Business** | **wow.vip@foxmail.com** |
| 🐙 **GitHub** | [https://github.com/yzsp-ai](https://github.com/yzsp-ai) |
| 💖 **打赏 / Support** | [afdian.com/a/yzsp-ai](https://afdian.com/a/yzsp-ai) |

## 📄 License

[MIT](LICENSE) · © 2026 [yzsp-ai](https://github.com/yzsp-ai)
