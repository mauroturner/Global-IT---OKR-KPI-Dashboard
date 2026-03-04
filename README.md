# Global IT - Comms & Change Champions Dashboard
### **Advanced BI Governance & Dynamic Engagement Analytics**

[![Power BI](https://img.shields.io/badge/Power_BI-PBIP-yellow?logo=powerbi)](https://powerbi.microsoft.com/)
[![AI-Orchestrated](https://img.shields.io/badge/AI-Orchestrated_via_MCP-blueviolet)](https://modelcontextprotocol.io/)
[![Organization](https://img.shields.io/badge/Organization-Accenture-purple)](https://www.accenture.com/)

## 🎯 Executive Overview
This project delivers a high-governance analytics ecosystem designed to monitor and measure the engagement of the **Global IT - Comms & Change Champions** network. 

Unlike traditional static dashboards, this system manages a **"Dynamic Denominator"** where the population of Champions and the set of survey questions rotate monthly. It bridges the gap between raw SharePoint data and strategic Change Management insights using a state-of-the-art **AI-Driven development workflow**.

---

## 🛠 Tech Stack & Methodology
* **Format:** Power BI Project (`.pbip`) using **TMDL** for semantic modeling and **PBIR (V2)** for report metadata.
* **Orchestration:** Google Antigravity + Microsoft Modeling MCP Server.
* **Version Control:** Git (line-by-line tracking of DAX and Visuals).
* **Architecture:** Star Schema with a specialized AI Context Layer.

---

## 🧠 AI-Driven Governance (`.ai_context/`)
This repository follows an **"AI-First" documentation strategy**. The `.ai_context/` directory acts as the "Brain" of the project, allowing LLMs to understand business rules, design standards, and data lineage without human intervention.

* **`00_index.md`**: The master routing guide for AI agents.
* **`business_context.md`**: Strategic goals and stakeholder definitions.
* **`data_dictionary.md`**: Deep dive into table relationships and the "Dynamic Denominator" logic.
* **`dax_standards.md`**: Strict engineering rules for DAX (Variables, naming, performance).
* **`viz_guidelines.md`**: Accenture branding, purple-scale palette, and UX/UI hierarchy.

---

## 📊 Data Architecture & Logic

### **The Star Schema**
The model is optimized to eliminate ambiguity and circular dependencies by using **Single Direction** filters across multiple fact tables.

| Table | Type | Key Logic |
| :--- | :--- | :--- |
| `Dim_Calendar` | Dimension | **Accenture Fiscal Year:** Sept 1st - Aug 31st. |
| `Dim_People` | Dimension | Enterprise ID bridge for identity uniqueness. |
| `cctracker` | Fact | Monthly log of "Active" Champions (The Denominator). |
| `answers` | Fact | SharePoint Online survey responses. |
| `questions` | Fact | Metadata for fixed (7) and dynamic monthly questions. |

### **Core KPIs**
The project implements high-precision DAX for engagement tracking:

1.  **Participation Rate:** $$\text{Participation Rate} = \frac{\text{Unique Champions with Responses in Month X}}{\text{Total Active Champions in Month X}}$$

2.  **Form Completion Index:** Evaluation of response depth (Real vs. Potential volume).
3.  **Attendance Rate:** Compliance validation by crossing event logs with active status.

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
    * Modify measures via TMDL files.
    * Update visuals via PBIR JSON edits.
4.  **Documentation:** Any new logic must be reflected in the corresponding `.md` file in `ai_context/` and the `00_index.md` updated accordingly.

---

## 👤 Lead Developer
**Mauro Turner** *AI Engineer & Data Scientist | Visualization Expert* *Accenture - Global IT Projects*