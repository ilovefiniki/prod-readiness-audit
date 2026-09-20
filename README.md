# 🚀 prod-readiness-audit: Autonomous Pre-Launch & Production Audit

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Compatible with Claude Code](https://img.shields.io/badge/Claude%20Code-Compatible-black?logo=anthropic)](https://claude.ai/code)
[![Compatible with Antigravity](https://img.shields.io/badge/Antigravity-Compatible-4285F4?logo=google)](https://deepmind.google)
[![Compatible with Cursor](https://img.shields.io/badge/Cursor-Compatible-000000)](https://cursor.com)
[![Standard: 2026 AI-Native](https://img.shields.io/badge/Standard-2026%20AI--Native-00b4d8)](#)

An autonomous **Agent Skill** that performs a comprehensive, multi-pillar pre-launch audit for web applications, SaaS platforms, and client websites before deploying to production.

It evaluates the codebase across **6 critical pillars** and produces an actionable `AUDIT_REPORT.md` with an executive release verdict (`READY FOR LAUNCH`, `LAUNCH WITH CAVEATS`, or `BLOCKED`).

Part of the **[ILF Studio](https://ilf-studio.com)** & **[ilovefiniki.com](https://ilovefiniki.com)** AI engineering toolset.

---

## ⚡ Quickstart (1-Liner Installation)

Run this in your target project root:

```bash
# For Antigravity & Gemini:
mkdir -p .agents/skills/prod-readiness-audit && curl -fsSL https://raw.githubusercontent.com/ilovefiniki/prod-readiness-audit/main/SKILL.md -o .agents/skills/prod-readiness-audit/SKILL.md

# For Claude Code:
mkdir -p .claude/skills/prod-readiness-audit && curl -fsSL https://raw.githubusercontent.com/ilovefiniki/prod-readiness-audit/main/SKILL.md -o .claude/skills/prod-readiness-audit/SKILL.md
```

Then trigger the audit in your AI agent:
```
prod-readiness-audit
```

---

## 🔍 The 6 Audit Pillars

```
1. Security & Privacy ➔ 2. SEO & GEO 2026 ➔ 3. Forms & CTA ➔ 4. PageSpeed & CWV ➔ 5. Media Optimization ➔ 6. Cookie & Analytics
```

| Pillar | What is Checked |
|---|---|
| **1. Security & Secrets** | Scans for tracked `.env` files, leaked API tokens (`sk-`, `ghp_`, `glpat-`), bot honeypots on all forms, SQL injection vectors, and security response headers (HSTS, CSP, X-Frame-Options). |
| **2. SEO & GEO 2026** | Validates single `<h1>`, title/meta limits, Schema.org JSON-LD structured data, AI crawler permissions (`/robots.txt`, `/llms.txt`), and BLUF answer structuring for AI engine citations. |
| **3. Forms & Contacts** | End-to-end dry-run submission testing via browser tools, verifies active response codes, and checks for placeholder facts (fake emails, dead CTA buttons, dummy phone numbers). |
| **4. PageSpeed & CWV** | Representative sampling via Lighthouse (LCP < 2.5s, CLS < 0.1, INP < 200ms, TTFB < 600ms). |
| **5. Media Optimization** | Flags legacy uncompressed PNG/JPG (>300KB), ensures explicit `width`/`height` attributes, and enforces high-priority hero image preloading without lazy-loading bottlenecks. |
| **6. Cookie & Analytics** | Verifies tracking scripts (GA4, Clarity, Pixels) are completely paused prior to user consent, and verifies developer opt-out bypass (`?admin=1`). |

---

## 📊 Sample Output (`AUDIT_REPORT.md`)

```markdown
# 🚀 Production Readiness Audit Report: MyPlatform

**Date:** 2026-09-20
**Overall Verdict:** 🟢 READY FOR LAUNCH

## Summary Scorecard

| Category | Status | Notes |
|---|---|---|
| 1. Security & Privacy | ✅ PASS | 0 leaked secrets, honeypots verified |
| 2. SEO & GEO 2026 | ✅ PASS | Schema JSON-LD and /llms.txt valid |
| 3. Forms & Contacts | ✅ PASS | Lead submission tested, 200 OK |
| 4. PageSpeed & CWV | ✅ PASS | Score 98 (LCP 0.8s, CLS 0.01) |
| 5. Media & Assets | ✅ PASS | All modern WebP/AVIF formats |
| 6. Cookie & Analytics | ✅ PASS | Tracking strictly gated behind consent |
```

---

## 🛠️ Cross-Agent Compatibility

| Agent / Environment | Installation Directory |
|---|---|
| **Claude Code** | `.claude/skills/prod-readiness-audit/SKILL.md` |
| **Antigravity & Gemini** | `.agents/skills/prod-readiness-audit/SKILL.md` |
| **Cursor** | `.cursor/rules/prod-readiness-audit.md` or `.agents/skills/prod-readiness-audit/SKILL.md` |
| **Windsurf** | `.windsurf/rules/prod-readiness-audit.md` |

---

## 📄 License

Released under the [MIT License](LICENSE). Maintained by [Vitaliy Alhimovich](https://github.com/ilovefiniki) at [ILF Studio](https://ilf-studio.com).
