# Skills · 分类整理版

存放面向 Agent 的 AI Skills 集合,按**用途**而不是按**来源仓库**分类。
所有内容均为**官方/原始仓库的只读镜像**,目的是在 TRAE / Claude Code / Cursor / Codex 等
Agent 中**可发现、可一键安装、可按域检索**。

> 个人仓库:<https://github.com/tianjing823/skills>
>
> 本仓库只做**分类、索引、归并**,不修改任何 skill 的 `SKILL.md` 内容。

---

## 来源溯源(Sources)

| 来源仓库 | 维护者 | 协议 | 数量 |
|---|---|---|---|
| [`anthropics/skills`](https://github.com/anthropics/skills) | Anthropic 官方 | Apache 2.0(docx/pdf/pptx/xlsx 子目录为 Source-Available) | 18 |
| [`addyosmani/agent-skills`](https://github.com/addyosmani/agent-skills) | Addy Osmani(Google Chrome 工程主管) | MIT | 24 |

合计 42 个 skill。所有改动通过 commit 记录可追溯到原仓库 commit hash。

---

## 分类索引

### 00-meta — 元 skill(如何发现/使用 skill)

- [`using-agent-skills`](./00-meta/using-agent-skills) — 把工作路由到正确 skill 的元方法论
- [`skill-creator`](./00-meta/skill-creator) — 创建/优化/评测 skill 的官方方法

### 10-lifecycle — 全生命周期 24 个工程师级 skill(Addy)

按 **DEFINE → PLAN → BUILD → VERIFY → REVIEW → SHIP** 顺序:

| 阶段 | Skill | 用途 |
|---|---|---|
| **DEFINE** | [`interview-me`](./10-lifecycle/interview-me) | 一次一问式需求反问,直到 ~95% 置信 |
|  | [`idea-refine`](./10-lifecycle/idea-refine) | 发散→收敛,把模糊想法打磨成可执行提案 |
|  | [`spec-driven-development`](./10-lifecycle/spec-driven-development) | 写 PRD(目标/命令/结构/代码风格/测试/边界)再写代码 |
| **PLAN** | [`planning-and-task-breakdown`](./10-lifecycle/planning-and-task-breakdown) | 把 spec 拆成可验收的小任务,排依赖 |
| **BUILD** | [`incremental-implementation`](./10-lifecycle/incremental-implementation) | 薄垂直切片:实现→测试→验证→commit |
|  | [`test-driven-development`](./10-lifecycle/test-driven-development) | Red-Green-Refactor,测试金字塔 80/15/5 |
|  | [`context-engineering`](./10-lifecycle/context-engineering) | 在合适时机喂给 Agent 合适信息 |
|  | [`source-driven-development`](./10-lifecycle/source-driven-development) | 每个框架决策都引用官方文档 |
|  | [`doubt-driven-development`](./10-lifecycle/doubt-driven-development) | CLAIM→EXTRACT→DOUBT→RECONCILE 抗幻觉 |
|  | [`frontend-ui-engineering`](./10-lifecycle/frontend-ui-engineering) | 组件架构、设计系统、WCAG 2.1 AA |
|  | [`api-and-interface-design`](./10-lifecycle/api-and-interface-design) | 契约优先设计、Hyrum's Law、One-Version Rule |
| **VERIFY** | [`browser-testing-with-devtools`](./10-lifecycle/browser-testing-with-devtools) | Chrome DevTools MCP 真实运行时测试 |
|  | [`debugging-and-error-recovery`](./10-lifecycle/debugging-and-error-recovery) | 五步排错:复现→定位→缩减→修复→防护 |
| **REVIEW** | [`code-review-and-quality`](./10-lifecycle/code-review-and-quality) | 五维度评审,~100 行/次,Nit/Optional/FYI |
|  | [`code-simplification`](./10-lifecycle/code-simplification) | Chesterton's Fence,Rule of 500 |
|  | [`security-and-hardening`](./10-lifecycle/security-and-hardening) | OWASP Top 10、三层边界 |
|  | [`performance-optimization`](./10-lifecycle/performance-optimization) | Core Web Vitals、measure-first |
| **SHIP** | [`git-workflow-and-versioning`](./10-lifecycle/git-workflow-and-versioning) | Trunk-based、原子 commit、~100 行 |
|  | [`ci-cd-and-automation`](./10-lifecycle/ci-cd-and-automation) | Shift Left、feature flag、质量门 |
|  | [`deprecation-and-migration`](./10-lifecycle/deprecation-and-migration) | Code-as-liability、强制 vs 建议下线 |
|  | [`documentation-and-adrs`](./10-lifecycle/documentation-and-adrs) | ADR、API 文档、inline doc 标准 |
|  | [`observability-and-instrumentation`](./10-lifecycle/observability-and-instrumentation) | 结构化日志、RED 指标、OpenTelemetry |
|  | [`shipping-and-launch`](./10-lifecycle/shipping-and-launch) | 上线前检查、灰度、回滚 |

### 20-documents — 文档四件套(Anthropic 官方生产级实现)

- [`docx`](./20-documents/docx) — 创建/读取/编辑 Word 文档(`.docx`)
- [`pdf`](./20-documents/pdf) — 创建/合并/拆分/表单/加密 PDF
- [`pptx`](./20-documents/pptx) — 创建/解析/编辑 PowerPoint 演示文稿
- [`xlsx`](./20-documents/xlsx) — 创建/编辑/分析电子表格(`.xlsx`/`.xlsm`/`.csv`/`.tsv`)

### 30-communication — 沟通与协作

- [`doc-coauthoring`](./30-communication/doc-coauthoring) — 苏格拉底式文档协作
- [`internal-comms`](./30-communication/internal-comms) — 4 类内部沟通模板(状态报告/3P/FAQ/Newsletter)

### 40-design — 设计与品牌

- [`frontend-design`](./40-design/frontend-design) — 有方向感、不模板化的 UI 设计
- [`canvas-design`](./40-design/canvas-design) — 视觉艺术 `.png` / `.pdf` 设计稿
- [`theme-factory`](./40-design/theme-factory) — 主题资产生成与匹配
- [`brand-guidelines`](./40-design/brand-guidelines) — 品牌规范合规(Anthropic 品牌色/字体)
- [`algorithmic-art`](./40-design/algorithmic-art) — p5.js 生成式艺术
- [`slack-gif-creator`](./40-design/slack-gif-creator) — Slack 优化 GIF 生成

### 50-development — 开发辅助工具

- [`claude-api`](./50-development/claude-api) — Claude API / Anthropic SDK 官方参考(强制读)
- [`mcp-builder`](./50-development/mcp-builder) — 用官方规范构建 MCP Server
- [`webapp-testing`](./50-development/webapp-testing) — Playwright 驱动的 Web 应用测试
- [`web-artifacts-builder`](./50-development/web-artifacts-builder) — 复杂多组件 Web 工件(React/Tailwind/shadcn)
- [`template-skill`](./50-development/template-skill) — 新 skill 的最小模板

---

## 安装使用

### 方式 A:用 Vercel Labs `skills` CLI(推荐,一行命令)

支持 70+ Agent,包括 Claude Code、Cursor、Codex、GitHub Copilot、TRAE、TRAE CN。

```bash
# 1) 安装 CLI(若未装)
npx -y skills --help

# 2) 安装本仓库全部 42 个 skill 到 TRAE
npx -y skills add tianjing823/skills -g -a trae-cn -y

# 3) 只装某个分类(以"全生命周期"为例)
npx -y skills add tianjing823/skills --skill source-driven-development -g -a trae-cn

# 4) 先浏览再装
npx -y skills add tianjing823/skills --list
```

### 方式 B:在 TRAE 中直接引用

TRAE 会按 `SKILL.md` 中的 `description` 字段自动匹配并激活,无需手动调用。
直接说"帮我做技术调研"会自动触发 `source-driven-development` 等。

### 方式 C:在 Claude Code / Cursor 中使用

```bash
# Claude Code(原生 marketplace)
/plugin marketplace add tianjing823/skills
/plugin install skills@tianjing823-skills

# Cursor
mkdir -p .cursor/skills && cp -r <sub-dir>/* .cursor/skills/
```

---

## 如何发现新 skill

```bash
npx skills find <keyword>            # 关键词搜索
npx skills find react --owner tianjing823   # 指定 owner
```

或浏览社区榜单:
- [skills.sh](https://skills.sh/) — 公开安装量排行榜
- [agentskills.io](https://agentskills.io/) — Agent Skills 开放标准

---

## 更新与维护

本仓库是**镜像型集合**,日常更新通过:

```bash
# 在 TRAE / 终端一键同步上游
npx skills update -g -a trae-cn
```

需要新增第三方 skill 时,沿用 `00-meta / 10-lifecycle / 20-documents / 30-communication / 40-design / 50-development` 数字前缀,字母序即分组顺序。
