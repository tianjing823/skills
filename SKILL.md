---
name: "skills-collection"
description: "Curated collection of 42 AI agent skills grouped by purpose: meta (skill discovery/creation), full engineering lifecycle (define/plan/build/verify/review/ship), document skills (docx/pdf/pptx/xlsx), communication, design, and development (Claude API, MCP, web testing). Use when the user wants to browse or install a specific skill from tianjing823/skills."
---

# Skills Collection

This repository contains the following skills:

- `00-meta/using-agent-skills/` - Maps incoming work to the right skill workflow and defines shared operating rules
- `00-meta/skill-creator/` - Create, modify, and measure skill performance with evals and variance analysis
- `10-lifecycle/interview-me/` - One-question-at-a-time interview that extracts what the user actually wants
- `10-lifecycle/idea-refine/` - Structured divergent/convergent thinking to turn vague ideas into concrete proposals
- `10-lifecycle/spec-driven-development/` - Write a PRD covering objectives, commands, structure, code style, testing, and boundaries before any code
- `10-lifecycle/planning-and-task-breakdown/` - Decompose specs into small, verifiable tasks with acceptance criteria and dependency ordering
- `10-lifecycle/incremental-implementation/` - Thin vertical slices: implement, test, verify, commit with feature flags and safe rollbacks
- `10-lifecycle/test-driven-development/` - Red-Green-Refactor, test pyramid (80/15/5), DAMP over DRY
- `10-lifecycle/context-engineering/` - Feed agents the right information at the right time via rules files and MCP integrations
- `10-lifecycle/source-driven-development/` - Ground every framework decision in official documentation with verifiable citations
- `10-lifecycle/doubt-driven-development/` - Adversarial fresh-context review of non-trivial decisions before they stand
- `10-lifecycle/frontend-ui-engineering/` - Component architecture, design systems, state management, WCAG 2.1 AA accessibility
- `10-lifecycle/api-and-interface-design/` - Contract-first design, Hyrum's Law, One-Version Rule, error semantics
- `10-lifecycle/browser-testing-with-devtools/` - Chrome DevTools MCP for live runtime data, DOM/network/console inspection
- `10-lifecycle/debugging-and-error-recovery/` - Five-step triage: reproduce, localize, reduce, fix, guard
- `10-lifecycle/code-review-and-quality/` - Five-axis review with severity labels and ~100-line change sizing
- `10-lifecycle/code-simplification/` - Chesterton's Fence, Rule of 500, reduce complexity while preserving exact behavior
- `10-lifecycle/security-and-hardening/` - OWASP Top 10 prevention, auth patterns, secrets management, three-tier boundaries
- `10-lifecycle/performance-optimization/` - Measure-first approach with Core Web Vitals targets and profiling workflows
- `10-lifecycle/git-workflow-and-versioning/` - Trunk-based development, atomic commits, the commit-as-save-point pattern
- `10-lifecycle/ci-cd-and-automation/` - Shift Left, Faster is Safer, feature flags, quality gate pipelines
- `10-lifecycle/deprecation-and-migration/` - Code-as-liability mindset, compulsory vs advisory deprecation, zombie code removal
- `10-lifecycle/documentation-and-adrs/` - Architecture Decision Records, API docs, document the *why*
- `10-lifecycle/observability-and-instrumentation/` - Structured logging, RED metrics, OpenTelemetry tracing
- `10-lifecycle/shipping-and-launch/` - Pre-launch checklists, feature flag lifecycle, staged rollouts, rollback procedures
- `20-documents/docx/` - Create, read, edit, or manipulate Word documents (.docx)
- `20-documents/pdf/` - Read, extract, merge, split, encrypt, OCR, or create PDF files
- `20-documents/pptx/` - Create, parse, edit, combine, or split PowerPoint presentations
- `20-documents/xlsx/` - Open, read, edit, fix, or create spreadsheets (.xlsx/.xlsm/.csv/.tsv)
- `30-communication/doc-coauthoring/` - Structured workflow for co-authoring documentation, proposals, specs
- `30-communication/internal-comms/` - Status reports, leadership updates, 3P updates, company newsletters, FAQs
- `40-design/frontend-design/` - Distinctive, intentional visual design with typography and aesthetic direction
- `40-design/canvas-design/` - Create beautiful visual art in .png and .pdf documents
- `40-design/theme-factory/` - Apply pre-set themes or generate new themes with colors and fonts
- `40-design/brand-guidelines/` - Apply official brand colors and typography to artifacts
- `40-design/algorithmic-art/` - Create algorithmic art using p5.js with seeded randomness
- `40-design/slack-gif-creator/` - Create animated GIFs optimized for Slack
- `50-development/claude-api/` - Reference for the Claude API / Anthropic SDK (model ids, pricing, streaming, tool use, MCP, caching)
- `50-development/mcp-builder/` - Guide for creating high-quality MCP servers in Python or Node/TypeScript
- `50-development/webapp-testing/` - Test and debug local web applications using Playwright
- `50-development/web-artifacts-builder/` - Build elaborate multi-component HTML artifacts with React/Tailwind/shadcn
- `50-development/template-skill/` - Minimal starting template for creating a new skill

Each subdirectory contains an independent `SKILL.md` file and related resources.

## Install

```bash
# Browse all skills
npx -y skills add tianjing823/skills --list

# Install a specific skill
npx -y skills add tianjing823/skills --skill source-driven-development -g -a trae-cn -y

# Install the full collection
npx -y skills add tianjing823/skills -g -a trae-cn -y
```

## Source

- Upstream 1: <https://github.com/anthropics/skills> (Anthropic official, 18 skills, Apache 2.0)
- Upstream 2: <https://github.com/addyosmani/agent-skills> (Addy Osmani, 24 skills, MIT)
- This repository is a read-only classification mirror. See `LICENSE` for full attribution.
