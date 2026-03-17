# 🤖 AI Personal Analyst Assistant
### Generative AI Integration with Amazon QuickSight — Operations Analytics

![Status](https://img.shields.io/badge/Status-Production-2D7D46?style=flat-square)
![Platform](https://img.shields.io/badge/Platform-Amazon%20QuickSight-FF9900?style=flat-square&logo=amazon)
![AI](https://img.shields.io/badge/AI-Generative%20LLM-146EB4?style=flat-square)
![Language](https://img.shields.io/badge/Prompt%20Engineering-Master%20Prompt-232F3E?style=flat-square)

---

## 📌 Overview

This project transforms static operational dashboards into an **intelligent, conversational analyst** — available on demand for every member of an operations team. Instead of manually navigating 3 separate QuickSight dashboards for 15–25 minutes per week, any associate can now get a complete, structured performance analysis in **under 2 minutes**.

> *"The assistant eliminates the gap between raw data and actionable decisions, giving each associate the power to understand and improve their own performance autonomously."*

---

## ⚡ Impact at a Glance

| Metric | Before | After |
|--------|--------|-------|
| Time to get full weekly analysis | 15–25 min (manual) | **< 2 min** |
| Benchmark interpretation | Knowledge-dependent | **Automatic (🟢🟡🔴)** |
| Defect root cause analysis | Fully manual | **Auto-grouped + ranked** |
| Week-over-week comparison | Not available | **Auto-generated** |
| Improvement suggestions | Manager sessions only | **On demand, anytime** |
| Data accessibility | Deep QuickSight nav required | **Natural language query** |

**For a team of 10: 130–230 minutes recovered per week — from consultation alone.**

---

## 🏗️ Architecture

```
Associate Query
      │
      ▼
┌─────────────────────────────┐
│  CONNECT Ops DATA Analyst   │
│     Assistant (AI Layer)    │
└─────────────┬───────────────┘
              │
    ┌─────────┼─────────┐
    ▼         ▼         ▼
┌────────┐ ┌──────┐ ┌──────────────┐
│CONNECT │ │Apeth │ │Connect       │
│Dashboard│ │Perf. │ │Compliance    │
└────────┘ └──────┘ └──────────────┘
    │         │         │
    └─────────┴─────────┘
              │
              ▼
   Structured Response
   Tables + Semaphores + Suggestions
```

---

## 📊 Data Sources

### Dashboard 1 — CONNECT
Queries taken · Jobs completed · DVs · DVs to Recover · Real Defects · Agreements/Disagreements · APL · Real APL · SPL (Takt) · Dispute breakdown · SLA Accomplished · Wasted Time · Root Causes

### Dashboard 2 — Apeth Performance
Total Audits · Processed Audits · Takt · PH · Dispute % · FFR · Accuracy · Borderline %

### Dashboard 3 — Connect Compliance
Answer Rate · Occupancy · Delivery % · Deficit Hours · SLA Adherence · ACW breakdown · LLI & ELO tracking · Behavior patterns

---

## 🧠 Prompt Architecture

The assistant is powered by a **Master Prompt** that controls 4 structured analysis modes:

### Option 1 — 📊 All Key Metrics Organized
Full semaphore dashboard across all 3 data sources. Each metric gets a 🟢🟡🔴 indicator based on standardized benchmark thresholds. Closes with a 3–5 line executive summary.

### Option 2 — 🎯 Improvement Areas This Week
- ✅ What you did well (specific numbers)
- ⚠️ Areas needing attention (metric + why it matters + concrete action)
- 🔴 Most frequent root causes
- 📈 Week-over-week comparison table
- 💡 3 prioritized suggestions ranked by impact

### Option 3 — 🔍 Complete Defect Detail
Full defect table with: Job ID · Agreement/Disagreement · OSE Response · Correct Event · Logic Error · URL SharePoint · DigDog Link · Dispute Label · Audit Status — plus root cause grouping and dispute impact on APL.

### Option 4 — 📈 Week-over-Week Comparison
Delta tables for all key metrics across all 3 dashboards, trend indicators (↑ ↓ →), and a narrative conclusion: what improved, what's concerning, what to maintain.

---

## 🔧 Prompt Engineering Design Principles

```
1. STRUCTURE FIRST
   → Define exact output format before writing the prompt
   → Each option has a fixed section schema the AI must follow

2. STANDARDIZED BENCHMARKS
   → Traffic-light thresholds are hardcoded in the prompt
   → Eliminates variability in how metrics are interpreted

3. ACTIONABILITY OVER COMPLETENESS
   → Always closes with 3 concrete, ranked suggestions
   → People act on recommendations, not data dumps

4. PROACTIVE ANOMALY DETECTION
   → AI is instructed to flag ⚠️ when negative trends appear
   → Without being asked

5. IDENTITY-AWARE
   → Greets by associate login name
   → Filters all data to that specific associate's records
```

---

## 📁 Repository Structure

```
ai-analyst-assistant/
│
├── prompts/
│   ├── master_prompt.md          # Full master prompt (sanitized)
│   ├── option_1_metrics.md       # Prompt for Option 1
│   ├── option_2_improvements.md  # Prompt for Option 2
│   ├── option_3_defects.md       # Prompt for Option 3
│   └── option_4_wow.md           # Prompt for Option 4
│
├── sample_data/
│   ├── connect_sample.csv        # Anonymized CONNECT data
│   ├── apeth_sample.csv          # Anonymized Apeth data
│   └── compliance_sample.csv     # Anonymized Compliance data
│
├── docs/
│   ├── case_study.pdf            # Full case study document
│   ├── architecture_diagram.png  # System architecture visual
│   └── sample_outputs/           # Screenshots of assistant responses
│
└── README.md
```

---

## 🗺️ Roadmap

| Phase | Milestone | Status |
|-------|-----------|--------|
| Phase 1 — MVP | Base prompts + dashboard integration | ✅ Complete |
| Phase 2 — Stabilization | Team testing + benchmark calibration | 🔄 In Progress |
| Phase 3 — Expansion | Team-level aggregated view + proactive alerts | 📅 Q2 2026 |
| Phase 4 — Scale | Replication to other teams + predictive analytics | 📅 Q3 2026 |

---

## 💡 Key Learnings

**1. Structure first, AI second**
The quality of output depends entirely on the quality of the prompt architecture. Defining the 4 modes and their exact output format was the highest-leverage work.

**2. Democratize before you automate**
The biggest win was access equity — associates who had never deeply used QuickSight got the same analytical depth as power users.

**3. Actionability over completeness**
Early versions surfaced all available data. Final design: 3 concrete suggestions per session. People act on recommendations, not data dumps.

---

## 📬 About This Project

Built as part of an AI integration initiative for an Amazon operations team. All data in this repository has been anonymized. The prompt architecture and system design are original work.

**Stack:** Amazon QuickSight · Generative AI (LLM) · Prompt Engineering · NLP · Operations Analytics

---

*Portfolio project — Data confidentiality applied. Original implementation: Amazon Global Realty Tech, 2026.*
