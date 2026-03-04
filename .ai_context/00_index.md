# Context Manifest: Global IT - OKR & KPI Dashboard

This document serves as the primary index and routing guide for the AI Agent. Before performing any action, consult this map to identify the appropriate reference file for the OKR tracking system.

## 📂 Knowledge Directory

| If you are asking about... | Consult this file | Description |
| :--- | :--- | :--- |
| **Strategy & OKRs** | `business_context.md` | Strategic objectives (AI Skills, Culture, Growth), KPI goals, and Target Values definitions. |
| **Architecture & DAX** | `dax_standards.md` | September-August Fiscal Year logic, Star Schema rules, Bridge Table filtering, and `ISINSCOPE` patterns. |
| **UX & KPI Visuals** | `viz_guidelines.md` | Conditional formatting (Red/Amber/Green), Gauge chart standards, and Accenture corporate styling. |
| **Data Dictionary** | `data_dictionary.md` | Schema for the 8 OKR tables (objectives, kpis, results, etc.), data types, and relationship mapping. |

## 🛠 AI Routing Instructions

1. **System Initialization:** Always read this file (`00_index.md`) at the start of a session to map the project's semantic structure.
2. **Logic Validation:** Before proposing any DAX measure (e.g., % Progress), validate the `Target_Value` logic and `Unit_ID` mapping in `data_dictionary.md`.
3. **Time Intelligence:** All time-based calculations must strictly follow the September-August Fiscal Year as defined in `dax_standards.md`.
4. **Baseline Reference:** For "Growth from Start" metrics, always reference the `Is_Beginning_Number` flag in the `results` table.
5. **Documentation Maintenance:** If you create new measures, helper tables, or logic nodes, you MUST update the `data_dictionary.md` and this `00_index.md` immediately to prevent context drift.

## 🚩 Project Status
- **Project Name:** Global IT OKR Tracking
- **Data Source:** `Datasets/okrs.xlsx` (Multi-table Excel)
- **Model Version:** 1.0 (Star Schema with Bridge Tables)
- **Fiscal Calendar:** September 1st to August 31st
- **Last Rules Update:** 2026-03-04