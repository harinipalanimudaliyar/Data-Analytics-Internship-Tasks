# DATA CLEANING & STRUCTURAL VALIDATION
## OVERVIEW:
The purpose of this task was to take a highly messy, unverified raw dataset and systematically apply data-cleansing techniques to ensure accuracy, formatting consistency, and full readiness for data analysis.

---

## FLOW:

### 1. Duplication Controls
*   **Identified:** 18 redundant rows threatening to skew statistical aggregations.
*   **Resolved:** Deployed deduplication parameters to isolate unique records.

### 2. Text Normalization
*   **Identified:** Erratic casing (e.g., `MCDONALD'S CORP`, `Bill SmITH`) and invisible whitespace padding.
*   **Resolved:** Applied string normalization to enforce standard Title Case and purge cell padding.

### 3. Computational Insulation
*   **Identified:** Broken mathematical outputs (`#DIV/0!`) fracturing downstream formulas.
*   **Resolved:** Wrapped metric arrays in logical error-handling formulas to bypass zero-division limits.

### 4. Schema Standardization
*   **Identified:** Mixed date patterns and hardcoded currency strings ($) blocking numeric calculations.
*   **Resolved:** Cast temporal fields into a uniform database standard (`YYYY-MM-DD`) and extracted non-numeric characters from financial rows.

---

## Operational Execution Roadmap

*   **Phase 1: Isolation** Archived the raw source data and generated a production replica for safe editing.
*   **Phase 2: Deduplication** Used the Excel Data Engine to permanently remove the 18 duplicate entries.
*   **Phase 3: Case Correction** Deployed `=PROPER(Cell)` to resolve erratic text typography.
*   **Phase 4: Whitespace Strip** Applied `=TRIM(Cell)` to wipe out hidden leading and trailing word gaps.
*   **Phase 5: Format Synchronization** Normalized all dates to `yyyy-mm-dd` and used Find & Replace to strip the `$` symbols.
*   **Phase 6: Math Correction** Rebuilt the profit margin formula using `=IFERROR((Profit/Revenue)*100,"")` to suppress active system errors.

---

## Matrix

| Function / Tool | Operational Intent | Code Syntax / Vector |
| :--- | :--- | :--- |
| `PROPER` | String Case Realignment | `=PROPER(B2)` |
| `TRIM` | Whitespace Suppression | `=TRIM(B2)` |
| `IFERROR` | Calculation Shielding | `=IFERROR((G2/F2)*100,"")` |
| **Deduplication** | Row Redundancy Suppression | Data Interface Action |
| **Find & Replace** | Currency Character Pruning | String Extraction Action |

---

## Repository Architecture
*   `/Raw_Data` — Source tracking sheet prior to engineering pipeline deployment.
*   `/Cleaned_Data` — Fully normalized and certified output asset (`Cleaned_dataset.xlsx`).
*   `README.md` — Project blueprint, methodology matrix, and validation log.

---

## Final Status Sign-Off
The dataset has successfully transitioned into a validated, audit-ready data product. All anomalies are suppressed, financial logic is verified, and the sheet is 100% prepared for dashboard ingestion.

**Project Verified By:** HARINI P  
**Position:** Data Analytics Intern  
**Project Track:** Task 1 Validation  

