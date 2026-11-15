
# AgriMonitor Rwanda

## Rwanda Crop Production, Utilisation and Post-Harvest Loss Monitoring System

| Project Detail | Information |
|---|---|
| **Student** | NTWARI Chris David |
| **Student ID** | 29378 |
| **Course** | INSY 8311 – Database Development with PL/SQL |
| **Instructor** | Eric Maniraguha |
| **Academic Year** | 2026–2027 |
| **Current Phase** | Phase 0 – Research, Data Source and Project Proposal |

---

## 1. Project Overview

AgriMonitor Rwanda is a proposed Oracle database system designed to organise and analyse agricultural crop production, harvest utilisation and post-harvest loss data in Rwanda.

The project will use real agricultural survey records from the National Institute of Statistics of Rwanda (NISR). Oracle SQL and PL/SQL will support data storage, validation, analysis, reporting and automated identification of high-loss cases.

The overall goal is to provide structured agricultural information that can support better analysis and agricultural planning.

## 2. Problem Statement

Rwandan farmers experience post-harvest losses caused by factors such as pests, harvesting practices, transportation and storage. The Ministry of Agriculture and Animal Resources reported that maize post-harvest losses accounted for 13.22% of production in its 2024–2025 annual report (MINAGRI, 2025).

Although national agricultural survey data can provide useful information about production, utilisation and losses, the downloaded NISR dataset is a wide flat file containing 98 columns. Analysing this information across crops, districts and loss causes can be difficult without a properly structured database.

AgriMonitor Rwanda proposes to address this challenge by transforming the survey data into a relational Oracle database and developing PL/SQL functionality for agricultural analysis, reporting and automated high-loss alerts.

## 3. Project Objectives

### 3.1 Main Objective

To design and develop an Oracle database system using PL/SQL that organises NISR crop production, utilisation and post-harvest loss survey records and generates analytical reports and automated alerts to support agricultural planning.

### 3.2 Specific Objectives

1. Analyse and normalise the NISR survey dataset into an appropriate Third Normal Form (3NF) relational database structure.
2. Create Oracle database tables and load the 35,584 downloaded survey records after data cleaning and validation.
3. Develop PL/SQL functions, procedures, cursors and packages to calculate and analyse production, utilisation and post-harvest loss indicators.
4. Implement database constraints, triggers and audit logging to improve data integrity and accountability.
5. Develop a Smart Post-Harvest Loss Alert System that identifies records meeting validated high-loss criteria.
6. Present relevant agricultural indicators and generated alerts through an analytical dashboard, subject to successful database connectivity.

## 4. Data Source

**Dataset:** Season B: Crop Production  
**Provider:** National Institute of Statistics of Rwanda (NISR)  
**Survey:** Seasonal Agricultural Survey 2023/2024  
**Reference Period:** March–June 2024  
**Downloaded CSV:** 35,584 records and 98 columns  
**Geographical Coverage:** 5 provinces and 30 districts.

**Dataset link:** https://data.gov.rw/datasets/eb96d559-71aa-430e-b00c-09da8fbeaf1a

The dataset contains agricultural information relating to crop production, harvest utilisation and post-harvest losses.

The downloaded dataset is a historical survey snapshot, not a live farm-monitoring feed. Consequently, the system's reports and alerts will be generated from recorded survey values rather than real-time farm measurements.

Additional dataset information and processing notes are maintained in [`data/README.md`](data/README.md).

## 5. Proposed Innovation

### Smart Post-Harvest Loss Alert System

The main innovation of AgriMonitor Rwanda is an automated alert mechanism implemented inside the Oracle database.

The proposed system will:

- Analyse recorded production and post-harvest loss information.
- Apply configurable loss thresholds based on validated dataset indicators.
- Identify records that meet the defined high-loss conditions.
- Store generated alerts in a dedicated `LOSS_ALERT` table.
- Use Oracle `DBMS_SCHEDULER` to run the alert-generation procedure periodically.

**Dashboard layer:** Power BI is proposed to display production indicators, loss percentages, utilisation patterns and generated alerts, subject to successful Oracle database connectivity. An alternative will be considered if the required connection cannot be established.

The business rules and alert calculations will remain in PL/SQL. The dashboard will primarily present the results.

## 6. Proposed Database Design

The following tables are preliminary candidates. Their final structure will be determined after dataset inspection, normalisation and ERD development.

| Proposed Table | Purpose |
|---|---|
| `PROVINCE` | Stores province information. |
| `DISTRICT` | Stores districts and their province relationships. |
| `PLOT` | Stores agricultural plot information where supported by the dataset. |
| `CROP` | Stores crop names and categories. |
| `CROP_PRODUCTION` | Stores crop production and harvest information. |
| `UTILISATION` | Stores harvest utilisation information. |
| `LOSS_CAUSE` | Stores post-harvest loss categories. |
| `PRODUCTION_LOSS` | Stores recorded loss quantities and related information. |
| `ALERT_THRESHOLD` | Stores configurable high-loss thresholds. |
| `LOSS_ALERT` | Stores alerts generated by the PL/SQL alert process. |
| `AUDIT_LOG` | Stores relevant database change records. |
| `STG_SEASON_B` | Temporarily holds source data during the loading process. |

A `FARMER` table will only be included if the dataset structure and project privacy requirements justify retaining farmer-level records.

## 7. Planned PL/SQL Development

| PL/SQL Feature | Planned Implementation |
|---|---|
| Functions | `fn_loss_percentage` to calculate loss percentage and `fn_utilisation_share` to calculate utilisation proportions. |
| Procedures | `sp_load_from_staging`, `sp_generate_loss_alerts` and `sp_district_loss_report`. |
| Cursors | Process production and loss records for crop and district summaries. |
| Packages | `pkg_agrimonitor` to organise related functions and procedures. |
| Triggers | Enforce validated data-integrity rules and record relevant changes in the audit log. |
| Exceptions | Handle missing records, invalid values and custom data-validation errors. |
| Scheduler | Use `DBMS_SCHEDULER` to execute the alert-generation procedure periodically. |

All calculations, validation rules and thresholds will be based on verified dataset definitions and appropriate business rules.

## 8. Repository Structure

The repository will be organised as follows:

```text
ntwari_29378_agriMonitor/
│
├── README.md
│
├── phase0_research_proposal/
│   ├── research_log.md
│   ├── proposal/
│   └── presentation/
    └──  about_dataset

│
├── phase1_business_modeling/
│   ├── bpmn_diagram/
│   └── uml_diagrams/
│
├── phase2_data_design/
│  
│
├── phase3_pdb_creation/
│  
│
├── phase4_tables_data_loading/
│  
│
├── phase5_plsql_development/
│  
│
├── phase6_triggers_auditing/
│   
│
├── phase7_final_documentation/
│  
│
└── scripts/
```

The repository will contain project documentation, approved dataset files or samples, database scripts, diagrams, PL/SQL code and innovation documentation. Files containing unnecessary identifying information will not be published.

## 9. Project Implementation Phases

| Phase | Main Activities | Status |
|---|---|---|
| Phase 0 | Research, dataset selection, proposal and presentation | In Progress |
| Phase I | Business process modelling using BPMN/UML | Planned |
| Phase II | Data analysis, normalisation, ERD and data dictionary | Planned |
| Phase III | Oracle Pluggable Database creation | Planned |
| Phase IV | Table creation, data loading and validation | Planned |
| Phase V | PL/SQL functions, procedures, cursors and packages | Planned |
| Phase VI | Triggers, restriction rules and auditing | Planned |
| Phase VII | Final documentation, innovation demonstration and presentation | Planned |

## 10. References

Benimana, G. U., Ritho, C., & Irungu, P. (2021). Assessment of factors affecting the decision of smallholder farmers to use alternative maize storage technologies in Gatsibo District-Rwanda. *Heliyon, 7*(10), e08235. https://doi.org/10.1016/j.heliyon.2021.e08235

Benimana, G. U., Ritho, C., & Irungu, P. (2023). Impact of adopting maize hermetic storage technologies on smallholder farmers' income in Gatsibo District, Rwanda. *Heliyon, 9*(3), e14592. https://doi.org/10.1016/j.heliyon.2023.e14592

e-HingiriSoko. (n.d.). *e-HingiriSoko: Digital markets ecosystem platform*. https://ehingirisoko.digital/

Ministry of Agriculture and Animal Resources. (2025). *Annual report 2024–2025*. Government of Rwanda. https://www.minagri.gov.rw/fileadmin/user_upload/Minagri/Publications/Annual_Reports/Annual_report_2024-2025_Final.pdf

National Institute of Statistics of Rwanda. (2026). *Season B: Crop Production* [Dataset]. Rwanda Data Sharing Platform. https://data.gov.rw/datasets/eb96d559-71aa-430e-b00c-09da8fbeaf1a

Oracle. (n.d.). *DBMS_SCHEDULER*. Oracle Database 21c documentation. https://docs.oracle.com/en/database/oracle/oracle-database/21/arpls/DBMS_SCHEDULER.html

---

**Project:** AgriMonitor Rwanda  
**Student ID:** 29378  
**Course:** INSY 8311 – Database Development with PL/SQl

