# Phase0 Lab — Product Planning

## Vision

Phase0 Lab 是一個開源組織，專注於打造 **AI Native 產品規劃工具**。

「Phase 0」是產品開發的 Fuzzy Front End — 發現、驗證、規劃的階段。我們的目標是用 AI Native 的方式重新定義這個階段，讓產品從構想到實作的路徑更短、更清晰。

**Tagline:** From idea to spec. From spec to code.

## Problem

### PM 的困境

- PM 花 40-60% 時間在「context 考古」— 翻 Slack、會議記錄、散落的文件
- 現有 AI 工具是「文件優先」— 幫你寫得更快，但不幫你想得更清楚
- 開發者已有 Cursor、Claude Code 等成熟工具，但規劃端的 AI 工具落後 2 年以上

### 市場缺口

| 維度 | 現狀 | 缺口 |
|------|------|------|
| PRD 生成 | ChatPRD、Notion AI 已解決文件層面 | 缺少 context 自動聚合 |
| 用戶研究 | Dovetail、BuildBetter 是獨立工具 | 未整合進規劃流程 |
| 競品分析 | Crayon 很強但封閉 | 與 spec 撰寫脫節 |
| 規劃→程式碼 | Spec Kit、Kiro 從開發端橋接 | 規劃端完全空白 |
| Agentic 能力 | 僅 25% PM 工具有自主行動能力 | 最大的空白市場 |
| 開源方案 | 專案管理有 Plane，spec-driven 有 Spec Kit | 沒有開源的 Phase 0 toolkit |

## Positioning

### AI Native vs AI Enhanced

- **AI Enhanced**: 在既有產品上加 AI 功能（如 Jira 加 AI 摘要、Notion 加 Notion AI）
- **AI Native**: 從第一天就以 AI 為核心設計，拿掉 AI 產品就不存在

Phase0 Lab 的工具是 AI Native — AI 不是附加功能，而是產品的核心運作方式。

### 為什麼是開源

1. 這個領域完全沒有開源方案
2. 開發者社群已習慣開源工具鏈（Claude Code、Spec Kit 等）
3. 開源能更快建立社群信任與採納
4. 與商業工具（ChatPRD $15-24/mo、Telos $95+/mo）形成差異化

## Architecture

四層架構：

```
┌─────────────────────────────────────────────────┐
│  Layer 4: Implementation Bridge                 │
│  Spec → Claude Code / Cursor 任務拆解與導入       │
├─────────────────────────────────────────────────┤
│  Layer 3: Living Specifications                 │
│  AI 生成會隨 context 更新的活文件（PRD、Story）    │
├─────────────────────────────────────────────────┤
│  Layer 2: Discovery & Validation                │
│  用戶研究綜合、競品分析、假設驗證、市場缺口分析      │
├─────────────────────────────────────────────────┤
│  Layer 1: Context Intelligence                  │
│  自動聚合 Slack、GitHub、會議紀錄、文件、程式碼     │
└─────────────────────────────────────────────────┘
```

## Products

### phase0-spec (Priority: High)

AI 驅動的 living specification 系統。

- 從 context 生成 PRD、User Story、Acceptance Criteria
- Spec 是活文件，隨 context 變化自動更新
- 輸出格式相容 Spec Kit、OpenSpec 等 spec-driven development 工具
- CLI + Claude Code skill 形式發佈

### phase0-discovery (Priority: High)

Context 聚合與產品 discovery agent。

- 從 Slack、GitHub Issues、會議紀錄自動聚合 context
- 建立產品知識圖譜（用戶、問題、功能、指標、決策的關聯）
- 消除 PM 40-60% 的 context 考古時間

### phase0-radar (Priority: Medium)

開源競品監控工具。

- 追蹤 GitHub releases、ProductHunt、changelog、blog
- 自動生成競品動態摘要
- 整合進 spec 撰寫流程

### phase0-bridge (Priority: Medium)

規劃到實作的橋接層。

- 將 spec 自動拆解為開發任務
- 直接導入 Claude Code / Cursor 的工作流程
- 雙向同步：程式碼變更反饋更新 spec

## Target Audience

1. **Solo PM / 小團隊 founder** — 需要 AI 同時扮演研究員、分析師、spec writer
2. **開發者兼 PM** — 已用 AI 寫程式，需要同等水準的 AI 規劃工具
3. **Full-Stack Product Lead** — 2026 新興角色，同時掌管規劃、設計、工程

## Competitive Landscape

| 工具 | 類型 | 價格 | 差異點 |
|------|------|------|--------|
| ChatPRD | 文件優先，SaaS | $15-24/mo | 最大用戶群，但僅生成靜態文件 |
| Telos | Context 優先，SaaS | $95+/mo | 聚合 Slack/GitHub，但昂貴且封閉 |
| Spec Kit | Spec-driven，開源 | Free | 從開發端橋接，不涵蓋 discovery |
| Kiro | Spec-driven，AWS | Free (preview) | IDE 整合，但不涵蓋 Phase 0 |
| **Phase0 Lab** | **AI Native，開源** | **Free** | **唯一涵蓋 discovery→spec→code 的開源方案** |

## Brand Assets

- **Organization**: Phase0 Lab
- **Domains**: phase0.dev (main), ph0.io (API/service), ph0.app (application)
- **GitHub**: github.com/phase0-lab
- **Email**: kyle@phase0.dev

## Timeline (Draft)

- **2026 Q2**: 首頁上線、phase0-spec MVP（Claude Code skill 形式）
- **2026 Q3**: phase0-discovery MVP、社群建立
- **2026 Q4**: phase0-radar、phase0-bridge 啟動
- **2027 Q1**: 整合版 Phase0 toolkit

## References

- [Front End Innovation (Wikipedia)](https://en.wikipedia.org/wiki/Front_end_innovation)
- [Spec-Driven Development with Spec Kit (GitHub Blog)](https://github.blog/ai-and-ml/generative-ai/spec-driven-development-with-ai-get-started-with-a-new-open-source-toolkit/)
- [AI PM Tools Directory](https://aipmtools.org/articles/future-of-ai-product-management)
- [ChatPRD](https://www.chatprd.ai/)
- [Telos](https://www.telos-ai.org/)
