# Project: Global IT - OKR & KPI Strategic Tracking

## Objective
Establish a centralized, high-governance tracking system for Global IT's strategic objectives. This dashboard measures progression toward 2026 goals across three main pillars: AI Capabilities, Culture of Engagement, and Career Growth.

## Strategic Pillars (Objectives)
1. **Enhance AI Skills and Capabilities:** Increasing AI-related literacy and technical skills within the Global IT workforce (Source: Workday & Skills Studio).
2. **Foster a Culture of Engagement & Belonging:** Strengthening relationships and connectivity through events and surveys.
3. **Drive Personal Growth and Energize Careers:** Focusing on well-being, recognition, and professional integration (NJX).

## Stakeholders & Persona
- **Lead:** Mauro Turner (AI Engineer & Data Scientist).
- **Environment:** Accenture Corporate (Fiscal Year: September - August).
- **Audience:** Global IT Leadership, HR Leads, and Change Management teams.

## Key Business Logic: The "Star Schema Strategy"
This project transitions from flat-file Excel tracking to a relational analytical model:
1. **Baseline Logic (`Is_Beginning_Number`):** Progression is measured against a fixed starting point (Nov 2025). Net growth is calculated as `Current Value - Baseline Value`.
2. **Multi-Entity Ownership:** Unlike standard KPIs, these metrics can have multiple **Owners** and **Sources**. This is handled via bridge tables (`kpi_owners`, `kpi_sources`) to ensure no data duplication during filtering.
3. **Time Series Normalization:** Monthly data is unpivoted in the `results` table. All time-intelligence must align with the **September-August Fiscal Year**.
4. **Mixed Unit Handling:** The model supports both **Percentage** (0.0 to 1.0) and **Count** (Integer) units. DAX measures must detect the `Unit_ID` to apply correct formatting and aggregation logic.

## Language Policy
- **MANDATORY:** All DAX measures, table/column names, technical comments, and architecture documentation MUST be in **English**. 
- Spanish is only permitted for non-technical status updates with the Lead.