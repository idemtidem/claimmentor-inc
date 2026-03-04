# ClaimMentor Inc

> Company management repository for roadmap, strategy, and operations

## Purpose

This repository is the **central hub for ClaimMentor company management** — not code. The software product lives in a separate repository.

**What lives here:**
- Product roadmap and feature prioritization
- Feature requests from prospects and customers
- Market intelligence and industry developments
- Support issue tracking and patterns
- Website planning and content
- Strategic planning documents
- Competitive analysis

---

## Repository Structure

```
claimmentor-inc/
├── CLAUDE.md               # This file — agent instructions
├── .claude/
│   └── agents/             # Agent definitions
│       └── pipeline-coordinator.md
├── output/                 # Pipeline outputs (gitignored)
│   ├── intelligence.md     # Sub-Agent 1 output
│   ├── product_analysis.md # Sub-Agent 2 output
│   ├── customer_analysis.md # Sub-Agent 3 output
│   ├── market_analysis.md  # Sub-Agent 4 output
│   └── exec_brief.md       # Sub-Agent 5 output
├── presentations/          # Exec presentations and briefs
├── prospects/              # Sales pipeline and prospect tracking
│   └── [company-name].md   # One file per prospect
├── customers/              # Active customer profiles
│   └── [company-name].md   # One file per customer
├── roadmap/                # Product roadmap and planning
│   ├── current-quarter.md
│   ├── backlog.md
│   └── completed.md
├── features/               # Feature requests and specs
│   ├── requests/           # Incoming requests from customers/prospects
│   ├── approved/           # Features approved for development
│   └── shipped/            # Completed features
├── market/                 # Market intelligence
│   ├── competitors/
│   ├── trends/
│   └── news/
├── support/                # Support patterns and issues
│   ├── issues/
│   └── patterns.md
├── website/                # Website planning and content
│   ├── copy/
│   ├── pages/
│   └── assets/
└── strategy/               # Strategic documents
    ├── vision.md
    ├── quarterly-goals.md
    └── meeting-notes/
```

---

## Agent Architecture

This repository uses a **5-agent pipeline** for strategic and operational tasks. Claude Code coordinates specialized roles to transform raw inputs (customer feedback, market signals, support issues) into actionable plans.

### Execution Flow

```
[Sub-Agent 1: Intelligence Gatherer]
              ↓ organized inputs
   ┌──────────┼──────────┐
   ↓          ↓          ↓
[Sub-Agent 2] [Sub-Agent 3] [Sub-Agent 4]
 Product       Customer      Market
 Strategist    Success       Analyst
   └──────────┬──────────┘
              ↓ all analyses complete
  [Sub-Agent 5: Executive Synthesizer]
              ↓
    actionable recommendations
```

**Phase 1 — Sequential:** Sub-Agent 1 gathers and organizes all relevant inputs.

**Phase 2 — Parallel:** Sub-Agents 2, 3, and 4 analyze from their perspectives simultaneously.

**Phase 3 — Sequential:** Sub-Agent 5 synthesizes everything into clear recommendations.

---

### Sub-Agent 1 — Intelligence Gatherer

**Goal:** Collect, organize, and categorize incoming information.

**Inputs:** Raw feature requests, support tickets, news articles, competitor updates, customer conversations.

**Outputs:** Organized intelligence ready for analysis:
- Categorized feature requests with source and context
- Support issues grouped by theme
- Market developments summarized
- Competitor moves documented

**Pipeline output:** Write to `output/intelligence.md`

**Operating Principles:**
- **Capture context**: Who requested it? Why? What problem does it solve?
- **No filtering yet**: Gather everything, let analysts prioritize
- **Source attribution**: Always note where information came from
- **Timestamp everything**: When was this requested/observed?

---

### Sub-Agent 2 — Product Strategist *(parallel)*

**Goal:** Translate customer needs and market signals into product direction.

**Inputs:** Organized intelligence from Sub-Agent 1, current roadmap, company vision.

**Outputs:**
- Feature prioritization recommendations (impact vs effort)
- Roadmap updates and sequencing
- Trade-off analysis for competing priorities
- Dependencies and blockers identified

**Operating Principles:**
- **Customer problem first**: Features solve problems, not add checkboxes
- **80/20 thinking**: What's the smallest thing that delivers the most value?
- **Say no more than yes**: Protect focus, avoid feature bloat
- **Build for the market, not one customer**: Unless they're paying for it

**File Ownership:** `roadmap/`, `features/approved/`
**Pipeline output:** Write to `output/product_analysis.md`

---

### Sub-Agent 3 — Customer Success *(parallel)*

**Goal:** Represent the voice of customers and prospects in all decisions.

**Inputs:** Feature requests, support issues, customer conversations.

**Outputs:**
- Customer pain point analysis
- Feature request synthesis (multiple requests → single insight)
- Support pattern identification
- Customer health signals

**Operating Principles:**
- **Listen for the need behind the ask**: "I want feature X" often means "I need to solve Y"
- **Segment feedback**: Enterprise vs SMB, prospect vs customer, power user vs new user
- **Quantify when possible**: 1 customer asked vs 10 customers asked
- **Close the loop**: Track what we promised and delivered

**File Ownership:** `features/requests/`, `support/`
**Pipeline output:** Write to `output/customer_analysis.md`

---

### Sub-Agent 4 — Market Analyst *(parallel)*

**Goal:** Monitor competitive landscape and industry trends.

**Inputs:** News, competitor updates, industry reports, technology developments.

**Outputs:**
- Competitive intelligence summaries
- Market trend analysis
- Opportunity and threat identification
- Positioning recommendations

**Operating Principles:**
- **Facts over speculation**: What did competitors actually ship/announce?
- **So what?**: Every observation needs an implication for us
- **Watch for disruption**: AI, regulations, new entrants
- **Benchmark honestly**: Where are we ahead? Behind?

**File Ownership:** `market/`
**Pipeline output:** Write to `output/market_analysis.md`

---

### Sub-Agent 5 — Executive Synthesizer *(sequential, runs last)*

**Goal:** Combine all analyses into clear, actionable recommendations.

**Inputs:** Outputs from Sub-Agents 2, 3, 4.

**Outputs:**
- Executive summary with top 3-5 recommendations
- Decision-ready briefs (not more analysis)
- Trade-offs explicitly stated
- Proposed next steps with owners

**Operating Principles:**
- **Pyramid principle**: Lead with the answer, then supporting evidence
- **Decisions, not documents**: What do we need to decide?
- **Surface conflicts**: If analysts disagree, show both sides
- **Time-bound**: What needs decision now vs later?

**File Ownership:** `strategy/`
**Pipeline output:** Write to `output/exec_brief.md` (and optionally `output/presentation.html`)

---

## Invoking the Agent Pipeline

### Full Pipeline (Recommended for Major Decisions)

Run all 5 agents with file-based handoffs:

```bash
claude "Run the full strategic pipeline for: [TOPIC]. Write outputs to /output/"
```

**Examples:**
```bash
# Quarterly planning
claude "Run the full strategic pipeline for Q2 planning. Analyze feature requests, market trends, and customer feedback. Write outputs to /output/"

# Decision brief
claude "Run the full strategic pipeline to decide: Should we add Outlook integration? Write outputs to /output/"

# Competitive response
claude "Run the full strategic pipeline to analyze n2uitive's latest release and recommend response. Write outputs to /output/"
```

**Pipeline outputs:**
```
output/
├── intelligence.md      # Sub-Agent 1: Gathered inputs
├── product_analysis.md  # Sub-Agent 2: Roadmap & prioritization
├── customer_analysis.md # Sub-Agent 3: Customer voice & pain points
├── market_analysis.md   # Sub-Agent 4: Competitive & trends
├── exec_brief.md        # Sub-Agent 5: Synthesized recommendations
└── presentation.html    # Optional: Exec-ready presentation
```

**Important:** Phase 2 agents run in parallel with `run_in_background: false` to ensure completion before synthesis.

### Single-Agent Invocations

For focused tasks, invoke individual agents:

**Market analysis:**
```bash
claude "As the Market Analyst agent, research recent developments in [insurance claims AI / competitor name] and document in market/trends/"
```

**Customer synthesis:**
```bash
claude "As the Customer Success agent, synthesize the last 10 feature requests in features/requests/ and identify common themes."
```

**Executive briefing:**
```bash
claude "As the Executive Synthesizer, create a decision brief for [topic] incorporating product, customer, and market perspectives."
```

---

## Working Methods

### Feature Request Processing

```
1. Customer/prospect makes request
2. Intelligence Gatherer logs in features/requests/ with context
3. Customer Success analyzes need behind the ask
4. Product Strategist evaluates fit with roadmap
5. Executive Synthesizer recommends: build / defer / decline
6. If approved, move to features/approved/
```

### Market Intelligence Cycle

```
Weekly:
- Market Analyst scans for competitor updates, news
- Document in market/news/ or market/competitors/

Monthly:
- Executive Synthesizer creates market brief
- Product Strategist reviews for roadmap implications

Quarterly:
- Full competitive analysis refresh
- Strategy document updates
```

### Support Pattern Analysis

```
1. Support issues logged in support/issues/
2. Customer Success identifies patterns monthly
3. Patterns inform Product Strategist priorities
4. Systemic issues escalated to roadmap
```

---

## Document Standards

### Prospects

```markdown
# [Company Name]

> [One-line description: industry, size, use case]

## Status
- **Stage:** [Lead / Qualified / Demo Scheduled / Demo Completed / Proposal / Negotiation / Closed Won / Closed Lost]
- **Next Step:** [What needs to happen next]
- **Owner:** [Who owns this relationship]

## Company Profile
- **Industry:** [e.g., Workers Comp, P&C, Health]
- **Size:** [Employee count, claims volume, etc.]
- **Location:** [HQ location]
- **Current Solution:** [What they use today]

## Contacts

| Name | Title | Email | Phone | Notes |
|------|-------|-------|-------|-------|
| | | | | Decision maker / Champion / End user |

## Meeting Log

### YYYY-MM-DD — [Meeting Type]

**Attendees:** [Names]
**Recording:** [Path to recording if available]
**Transcript:** [Path to transcript if available]

#### Key Discussion Points
- [Point 1]
- [Point 2]

#### Their Pain Points
- [Pain 1]
- [Pain 2]

#### What They Liked
- [Feature/aspect that resonated]
- [Another positive reaction]

#### What They Didn't Like / Concerns
- [Objection or concern raised]
- [Missing feature or gap]

#### Requirements / Requests
| Requirement | Priority | Notes |
|-------------|----------|-------|
| | | |

#### Next Steps
- [ ] [Action item with owner]

---

## Deal Notes

**Why they'd buy:**
- [Reason 1]
- [Reason 2]

**Risks / Objections:**
- [Risk 1]
- [Risk 2]

**Estimated Deal Size:**
- [X] adjusters × $100/month = $[X]/month
- Annual: $[X]

**Timeline:**
- [Expected decision date or buying timeline]
```

### Customers

```markdown
# [Company Name]

> [One-line description]

## Account Status
- **Customer Since:** YYYY-MM-DD
- **Plan:** [Plan name / tier]
- **MRR:** $[X]
- **Health:** [Healthy / At Risk / Churned]
- **Owner:** [Account manager]

## Company Profile
- **Industry:** [e.g., Workers Comp, P&C, Health]
- **Size:** [Employee count, claims volume]
- **Users:** [Number of active users]

## Contacts

| Name | Title | Email | Role |
|------|-------|-------|------|
| | | | Champion / Admin / End user |

## Usage & Engagement
- **Monthly Recordings:** [X]
- **Last Active:** [Date]
- **Key Use Cases:** [How they use the product]

## Meeting / Interaction Log

### YYYY-MM-DD — [Meeting Type]
[Notes]

---

## Expansion Opportunities
- [Opportunity 1]
- [Opportunity 2]

## Risk Factors
- [Risk 1]
- [Risk 2]

## Feature Requests
- [Link to feature request 1]
- [Link to feature request 2]
```

### Feature Requests

```markdown
# [Feature Name]

**Requested by:** [Customer/Prospect name]
**Date:** YYYY-MM-DD
**Source:** [Call / Email / Support ticket / Demo feedback]

## The Ask
[What they literally asked for]

## The Need
[What problem they're trying to solve]

## Context
[Their use case, company size, current workflow]

## Priority Signals
- [ ] Multiple customers asked
- [ ] Blocking a deal
- [ ] Causing churn risk
- [ ] Competitive pressure

## Notes
[Any additional context]
```

### Market Intelligence

```markdown
# [Headline]

**Date:** YYYY-MM-DD
**Source:** [URL or publication]
**Category:** [Competitor / Trend / Regulation / Technology]

## Summary
[2-3 sentence summary]

## Implications for ClaimMentor
[What does this mean for us?]

## Recommended Action
[Watch / Respond / Ignore]
```

### Roadmap Items

```markdown
# [Feature Name]

**Status:** [Proposed / Approved / In Development / Shipped]
**Target:** [Quarter/Month]
**Owner:** [Product owner]

## Problem Statement
[What customer problem does this solve?]

## Success Metrics
[How will we know it worked?]

## Scope
[What's in / out of scope]

## Dependencies
[What needs to happen first?]
```

---

## Code of Conduct for Agents

### Accuracy & Honesty
- Never fabricate customer quotes or market data
- Distinguish fact from inference
- Acknowledge uncertainty

### Balanced Perspective
- Represent multiple viewpoints fairly
- Don't cherry-pick data to support a predetermined conclusion
- Surface disagreements, don't hide them

### Actionable Output
- Every analysis should lead to a recommendation
- "Interesting" is not enough — what should we do?
- Be specific: who, what, when

### Institutional Memory
- Document decisions and rationale
- Future you will thank present you
- Link related documents

---

## Edge Cases

- If customer feedback conflicts, surface both perspectives
- If market data is stale, note the date and recommend refresh
- If a feature request doesn't fit the vision, document why we declined
- If analysts disagree, Executive Synthesizer presents both views with recommendation
