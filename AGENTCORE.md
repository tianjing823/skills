# Amazon Bedrock AgentCore 加载指南

> 本仓库专为 **Amazon Bedrock AgentCore** 的 `add skill --git` 来源设计。
> 每个子目录里的 `SKILL.md` 都符合 [AgentSkills 开放规范](https://agentskills.io/),
> AgentCore CLI 拉取后会自动识别。

## 4 个 Skill 来源速查

AgentCore Harness 的 skill 有 4 种来源(参考
[`awslabs/agentcore-samples` 13-aws-skills 示例](https://github.com/awslabs/agentcore-samples/tree/main/01-features/01-harness/01-advanced-examples/13-aws-skills)):

| 来源 | CLI 标志 | 形态 | 何时用 |
|---|---|---|---|
| **AWS Skills** | `--aws-skills [paths]` | 平台内置技能包(无需 URL) | 想要 AWS 域专业知识(CDK / Lambda / Bedrock 等),由 `aws/agent-toolkit-for-aws` 维护 |
| **Git (HTTPS)** | `--git <url>` + `--git-path <subdir>` | 公开/私有 Git 仓库内子目录里的 `SKILL.md` | 跨团队共享自定义 skill,本仓库就是这种 |
| **Amazon S3** | `--s3 <uri>` | `s3://bucket/path/SKILL.md` 对象 | 企业内私有 skill 分发,通过 S3 做权限管控 |
| **Path** | `--path <dir>` | Harness VM 镜像内已存在的目录 | 镜像预装 skill、Agent 启动即用(零运行时下载) |

4 种来源可在同一次 `add skill` 中混合(union),互不冲突。

## 本仓库走 `Git (HTTPS)` 来源

`https://github.com/tianjing823/skills` 仓库的每个 `skills/<cat>/<name>/`
子目录下都有一份合规的 `SKILL.md`。**不要**把整个仓库根目录当作一个 skill 加载,
AgentCore 走的是单 skill 模型 —— 一次 `add skill` = 一个 skill。

## 一条命令加载一个 skill

```bash
# 0) 安装 AgentCore CLI(若未装)
npm install -g @aws/agentcore

# 1) 先有一个 harness(在 agentcore 项目根目录执行)
agentcore add harness --name my-harness --model-provider bedrock

# 2) 从本仓库加载某个 skill
agentcore add skill \
  --harness my-harness \
  --git https://github.com/tianjing823/skills \
  --git-path skills/10-lifecycle/source-driven-development

# 3) 部署
agentcore deploy
```

`--git-path` 接受**仓库内的子目录路径**;该目录下必须有 `SKILL.md`,CLI 会
自动 clone 仓库后定位并校验 frontmatter(name + description)。

## 全部 42 个 skill 的 `add skill` 命令

把 `<HARNESS>` 替换成你自己的 harness 名即可直接复制使用。

### 00-meta · 元 skill(2)

```bash
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/00-meta/skill-creator
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/00-meta/using-agent-skills
```

### 10-lifecycle · 工程师全生命周期(23)

```bash
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/api-and-interface-design
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/browser-testing-with-devtools
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/ci-cd-and-automation
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/code-review-and-quality
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/code-simplification
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/context-engineering
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/debugging-and-error-recovery
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/deprecation-and-migration
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/documentation-and-adrs
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/doubt-driven-development
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/frontend-ui-engineering
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/git-workflow-and-versioning
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/idea-refine
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/incremental-implementation
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/interview-me
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/observability-and-instrumentation
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/performance-optimization
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/planning-and-task-breakdown
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/security-and-hardening
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/shipping-and-launch
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/source-driven-development
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/spec-driven-development
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/10-lifecycle/test-driven-development
```

### 20-documents · 文档四件套(4)

```bash
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/20-documents/docx
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/20-documents/pdf
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/20-documents/pptx
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/20-documents/xlsx
```

### 30-communication · 沟通与协作(2)

```bash
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/30-communication/doc-coauthoring
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/30-communication/internal-comms
```

### 40-design · 设计与品牌(6)

```bash
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/40-design/algorithmic-art
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/40-design/brand-guidelines
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/40-design/canvas-design
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/40-design/frontend-design
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/40-design/slack-gif-creator
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/40-design/theme-factory
```

### 50-development · 开发辅助(5)

```bash
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/50-development/claude-api
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/50-development/mcp-builder
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/50-development/template-skill
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/50-development/web-artifacts-builder
agentcore add skill --harness <HARNESS> --git https://github.com/tianjing823/skills --git-path skills/50-development/webapp-testing
```

## 批量加载脚本

```bash
# 加载全部 42 个 skill
HARNESS=my-harness
for p in $(git ls-remote --refs https://github.com/tianjing823/skills | head -1 >/dev/null && \
           curl -sS https://api.github.com/repos/tianjing823/skills/contents/skills | \
           jq -r '.[] | select(.type=="dir") | .path'); do
  for sub in $(curl -sS "https://api.github.com/repos/tianjing823/skills/contents/$p" | \
               jq -r '.[] | select(.type=="dir") | .path'); do
    agentcore add skill --harness "$HARNESS" \
      --git https://github.com/tianjing823/skills --git-path "$sub"
  done
done

agentcore deploy
```

或更省事的 shell 一次性循环(假设你已 clone 本仓库):

```bash
cd <clone>/skills-mirror
for d in skills/*/*/; do
  [ -f "$d/SKILL.md" ] || continue
  agentcore add skill --harness "$HARNESS" \
    --git https://github.com/tianjing823/skills --git-path "${d%/}"
done
```

## `SKILL.md` 格式规范

每份 `SKILL.md` 都遵循 AgentSkills 开放规范([agentskills.io](https://agentskills.io/)),
由 [Anthropic 官方 `anthropics/skills`](https://github.com/anthropics/skills) 与
[Addy Osmani `addyosmani/agent-skills`](https://github.com/addyosmani/agent-skills)
的源仓库镜像而来,包括:

- YAML frontmatter 必填字段:`name`(与目录名一致)、`description`(一句话 + 触发词)
- 可选 `version`、`metadata`(AWS 官方大量使用,做 service / task / persona 画像)
- Markdown 正文:`Overview` + `Routing`(user need → action 表)+ `Files` 索引
- `references/` 目录:详细材料外置,主 `SKILL.md` 保持精炼
- `assets/` 目录:模板、代码片段、字体等可执行资源

## 与其他加载方式的关系

| 工具 | 加载方式 | 兼容本仓库? |
|---|---|---|
| **Amazon Bedrock AgentCore** | `add skill --git <url> --git-path <subdir>` | ✅ 见上 |
| **Vercel `skills` CLI** | `npx skills add tianjing823/skills` | ✅ catalog 模式,`--skill <name>` 单选 |
| **Claude Code Plugin** | `/plugin marketplace add tianjing823/skills` | ✅ marketplace.json 已可发现 |
| **Cursor / Codex / Kiro** | `npx skills add tianjing823/skills` | ✅ 同 Vercel CLI |
| **TRAE / TRAE CN** | `npx skills add tianjing823/skills -g -a trae-cn` | ✅ |

## 参考链接

- [AgentCore CLI 源码 — `add skill` 实现](https://github.com/aws/agentcore-cli/blob/main/src/cli/commands/add/skill-action.ts)
- [AgentCore CLI 源码 — `--git` 校验](https://github.com/aws/agentcore-cli/blob/main/src/cli/commands/add/skill-command.ts)
- [AgentCore 官方示例 — Harness + Skills](https://github.com/awslabs/agentcore-samples/tree/main/01-features/01-harness/01-advanced-examples/13-aws-skills)
- [AgentCore 官方示例 — 自定义 Skill 安装](https://github.com/awslabs/agentcore-samples/tree/main/01-features/01-harness/01-advanced-examples/05-agent-skills)
- [AWS Skills 源仓库 `aws/agent-toolkit-for-aws`](https://github.com/aws/agent-toolkit-for-aws/tree/main/skills)
- [AgentSkills 开放规范](https://agentskills.io/)
