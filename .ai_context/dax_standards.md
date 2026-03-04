# DAX Engineering Standards (Global IT OKR Project)

## 1. Naming & Language Conventions
- **Measures:** Use square brackets and descriptive English names: `[Metric Name]`.
- **Variables:** Use `camelCase` for internal variables: `varCurrentActual`.
- **Technical Comments:** All logic explanations must be in **English**.
- **Calculated Columns:** Avoid whenever possible. Prioritize Power Query (M) or Measures.

## 2. Formatting & Structure
- **Block Pattern:** Always use `VAR` / `RETURN` blocks for clarity and performance.
- **Indentation:** Use 4 spaces or a tab for nested logic.
- **Time Intelligence:** Strictly follow the **September-August** Fiscal Year. 
  - Standard DAX time functions (`TOTALYTD`, etc.) must include the optional `YearEndDate` parameter: `"08-31"`.

## 3. Core Calculation Patterns

### A. Current Actual Value (Latest Reporting)
Goal: Get the most recent value for the current filter context, excluding the baseline.

```dax
Actual_Value_Latest = 
VAR varLatestDate = MAX('results'[Date])
RETURN
CALCULATE(
    SUM('results'[Actual_Value]),
    'results'[Date] = varLatestDate,
    'results'[Is_Beginning_Number] = FALSE
)
```

### B. Baseline Reference (Nov 2025)
Goal: Isolate the starting point for net growth analysis.

```dax
Baseline_Value = 
CALCULATE(
    SUM('results'[Actual_Value]),
    'results'[Is_Beginning_Number] = TRUE
)
```

### C. KPI Progress % (Strategic Logic)
Goal: Calculate achievement vs. Target. 
- **Growth KPIs:** (Actual - Baseline) / (Target - Baseline)
- **Completion KPIs:** Actual / Target

```dax
KPI_Progress_Pct = 
VAR varCurrent = [Actual_Value_Latest]
VAR varBaseline = [Baseline_Value]
VAR varTarget = MAX('kpis'[Target_Value])
VAR varUnit = MAX('kpis'[Unit_ID]) -- 1: Percentage, 2: Count

RETURN
IF(
    ISINSCOPE('kpis'[KPI_ID]),
    SWITCH( TRUE(),
        -- Logic for Percentage-based completion (e.g., TQ Courses)
        varUnit = 1, DIVIDE(varCurrent, varTarget, 0),
        -- Logic for Count-based growth (e.g., Events or Skills)
        varUnit = 2, DIVIDE(varCurrent - varBaseline, varTarget - varBaseline, 0),
        BLANK()
    ),
    -- Aggregation for Totals/Objectives: Average of child KPI progress
    AVERAGEX(VALUES('kpis'[KPI_ID]), [KPI_Progress_Pct])
)
```

## 4. Visual Standards (Status & Formatting)

### RAG Status (Red-Amber-Green)
Goal: KPI health based on progress.
- **Green:** >= 90%
- **Amber:** 70% - 89%
- **Red:** < 70%

```dax
KPI_Status_Color = 
VAR varProgress = [KPI_Progress_Pct]
RETURN
SWITCH( TRUE(),
    varProgress >= 0.90, "#008000", -- Green
    varProgress >= 0.70, "#FFBF00", -- Amber
    "#FF0000" -- Red
)
```

## 5. Aggregation Safeguards
- **ISINSCOPE:** Always use `ISINSCOPE('kpis'[KPI_ID])` or `ISINSCOPE('objectives'[Objective_ID])` to prevent non-sensical sums of percentages at the Grand Total level.
- **Divide:** Always use the `DIVIDE(n, d, alternate_result)` function to prevent division by zero errors.