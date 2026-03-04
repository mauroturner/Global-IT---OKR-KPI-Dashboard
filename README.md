# Global IT - OKR & KPI Dashboard
### **Advanced BI Governance & Strategic Performance Analytics**

[![Power BI](https://img.shields.io/badge/Power_BI-PBIP-yellow?logo=powerbi)](https://powerbi.microsoft.com/)
[![AI-Orchestrated](https://img.shields.io/badge/AI-Orchestrated_via_MCP-blueviolet)](https://modelcontextprotocol.io/)
[![Organization](https://img.shields.io/badge/Organization-Accenture-purple)](https://www.accenture.com/)

## 🎯 Executive Overview
This project delivers a high-governance analytics ecosystem designed to monitor and measure the strategic progression of the **Global IT Roadmap**. 

By tracking Objectives and Key Results (OKRs), this system transforms raw metric logs into actionable insights. It utilizes a sophisticated **Many-to-Many architecture** to handle complex ownership and data sourcing, all while maintaining a strict **AI-Driven development workflow** for maximum scalability and transparency.

---

## 🛠 Tech Stack & Methodology
* **Format:** Power BI Project (`.pbip`) using **TMDL** for semantic modeling and **PBIR (V2)** for report metadata.
* **Orchestration:** Google Antigravity + Microsoft Modeling MCP Server.
* **Version Control:** Git (line-by-line tracking of DAX, JSON metadata, and Visuals).
* **Architecture:** Star Schema with Bridge Tables and a specialized AI Context Layer.

---

## 🧠 AI-Driven Governance (`.ai_context/`)
This repository follows an **"AI-First" documentation strategy**. The `.ai_context/` directory acts as the "Brain" of the project, allowing LLMs to understand business rules, design standards, and data lineage without human intervention.

* **`00_index.md`**: The master routing guide for AI agents.
* **`business_context.md`**: Strategic pillars and Global IT roadmap definitions.
* **`data_dictionary.md`**: Deep dive into the `results` fact table and growth/completion logic.
* **`dax_standards.md`**: Strict engineering rules for DAX (Variables, naming, performance).
* **`viz_guidelines.md`**: Accenture branding, purple-scale palette, and UX/UI hierarchy.

---

## 📊 Data Architecture & Logic

### **The Star Schema (Global IT OKRs)**
The model is optimized to handle high-granularity performance tracking while maintaining clear dimensional filtering.

| Component | Tables | Key Logic |
| :--- | :--- | :--- |
| **Dimensional Hubs** | `objectives`, `kpis`, `units`, `Calendar` | **Accenture FY:** Starts Sept 1st. Grain: Daily/Month-Start. |
| **Bridge Tables** | `kpi_owners`, `kpi_sources` | Bi-directional filtering to allow multi-owner/source slicing. |
| **Lookup Tables** | `owners`, `sources` | Master metadata for stakeholder and origin identification. |
| **Fact Table** | `results` | Monthly progression log. Includes **Nov 2025 Baseline** flag. |

### **Core KPIs & DAX Logic**
The project implements high-precision DAX for performance tracking based on KPI types:

1.  **Growth KPI Progress:** Used when a baseline is required to measure improvement.
    $$\text{Progress \%} = \frac{\text{Current Actual} - \text{Baseline Actual}}{\text{Target} - \text{Baseline Actual}}$$

2.  **Completion KPI Progress:** Direct achievement toward a fixed goal.
    $$\text{Progress \%} = \frac{\text{Current Actual}}{\text{Target}}$$

---

## 🎨 Design System: Accenture Purples
The UI follows strict corporate identity guidelines to ensure professional delivery.

* **Primary Palette (Purples):** `#460073`, `#A055F5`, `#BE82FF`, `#DCAFFF`, `#A100FF`.
* **Neutral Palette:** `#FFFFFF`, `#F3F4F6`.
* **Typography:** Segoe UI / Semibold for high-impact headers.

---

## 🚀 How to Contribute (AI-First Workflow)
1.  **Setup:** Ensure you have the `Power BI Modeling MCP Server` configured in your host.
2.  **Context Loading:** Always point the agent to `.ai_context/00_index.md` before starting a task.
3.  **Development:**
    * Modify measures via **TMDL** files.
    * Update visuals via **PBIR** JSON edits.
4.  **Documentation:** Any new metric or bridge table logic must be reflected in the corresponding `.md` file in `ai_context/`.

---

## 👤 Lead Developer
**Mauro Turner**
*AI Engineer & Data Scientist | Visualization Expert*
*Accenture - Global IT Projects*