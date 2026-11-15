# RESEARCH LOG – AGRIMONITOR RWANDA

## Project Information

| Item | Details |
|---|---|
| Project Title | Rwanda Crop Production, Utilisation and Post-Harvest Loss Monitoring System |
| Project Short Name | AgriMonitor Rwanda |
| Student Name | NTWARI Chris David |
| Student ID | 29378 |
| Course | INSY 8311 – Database Development with PL/SQL |
| Academic Year | 2026–2027 |

## 1. Introduction

Agriculture plays an important role in Rwanda's economy and food security. However, agricultural production can be affected by losses occurring during harvesting, transportation, processing and storage. Understanding the quantities harvested, how crops are utilised and where losses occur is important for improving agricultural planning and post-harvest management.

This research examines existing studies, government information, agricultural digital platforms, available datasets and Oracle technical documentation relevant to the development of AgriMonitor Rwanda. The purpose is to establish the project's justification, identify existing solutions and determine how database technology and PL/SQL can support agricultural data analysis and post-harvest loss monitoring.

## 2. Review of Research Sources

### 2.1 Research Paper 1: Factors Affecting Adoption of Maize Storage Technologies

**APA Reference**

Benimana, G. U., Ritho, C., & Irungu, P. (2021). Assessment of factors affecting the decision of smallholder farmers to use alternative maize storage technologies in Gatsibo District-Rwanda. *Heliyon, 7*(10), e08235. https://doi.org/10.1016/j.heliyon.2021.e08235

**Source type:** Peer-reviewed research paper.

**Key findings:**  
The study investigates factors influencing smallholder farmers' decisions to adopt alternative maize storage technologies in Gatsibo District, Rwanda. It highlights the importance of suitable storage technologies in reducing post-harvest storage losses and improving food security. The research identifies the need to improve farmers' access to effective storage technologies.

**Relevance to AgriMonitor Rwanda:**  
This study provides evidence that post-harvest storage losses are a relevant agricultural challenge in Rwanda. It supports the need for a system that can organise and analyse information about crop production and losses.

**Identified research gap:**  
The study concentrates on maize storage technology adoption in Gatsibo District. AgriMonitor will address a broader information-management need by analysing different crops, districts, production utilisation patterns and reported post-harvest losses using a relational database.

### 2.2 Research Paper 2: Impact of Hermetic Storage Technologies on Farmers' Income

**APA Reference**

Benimana, G. U., Ritho, C., & Irungu, P. (2023). Impact of adopting maize hermetic storage technologies on smallholder farmers' income in Gatsibo District, Rwanda. *Heliyon, 9*(3), e14592. https://doi.org/10.1016/j.heliyon.2023.e14592

**Source type:** Peer-reviewed research paper.

**Key findings:**  
The research examines 301 randomly selected smallholder maize farmers in Gatsibo District. Its findings indicate that adopting hermetic storage technologies had a positive and statistically significant impact on income from stored maize among farmers who adopted them. The study also identifies factors such as training and access to credit as relevant to technology adoption.

**Relevance to AgriMonitor Rwanda:**  
The study demonstrates the importance of effective post-harvest management and provides further justification for monitoring crop losses. It also shows why reliable agricultural information can support better decisions.

**Identified research gap:**  
The study focuses on maize storage technology and its relationship with farmers' income. AgriMonitor will provide a database-based approach to analysing production, crop utilisation and losses across multiple crops and geographical areas.

### 2.3 Government Report: Rwanda Agricultural Performance and Post-Harvest Management

**APA Reference**

Ministry of Agriculture and Animal Resources. (2025). *Annual report 2024–2025*. Government of Rwanda. https://www.minagri.gov.rw/fileadmin/user_upload/Minagri/Publications/Annual_Reports/Annual_report_2024-2025_Final.pdf

**Source type:** Government report and agricultural statistics.

**Key findings:**  
The report identifies post-harvest losses, particularly in maize and rice, as an important agricultural challenge. It estimates maize post-harvest losses at 13.22% of total production, compared with a baseline of 13.80% in 2023. It identifies harvesting, storage, transportation, processing and sales as stages where losses occur.

**Relevance to AgriMonitor Rwanda:**  
These statistics provide national evidence supporting the importance of post-harvest loss monitoring. The report also identifies different stages of the agricultural process that can inform the project's data analysis and reporting requirements.

**Identified research gap:**  
Although the report provides national agricultural statistics and information about post-harvest management, AgriMonitor will focus on organising plot-level survey records and generating structured analytical reports by crop, district and loss category.

### 2.4 Existing System: e-HingiriSoko

**APA Reference**

e-HingiriSoko. (n.d.). *e-HingiriSoko: Digital markets ecosystem platform*. https://ehingirisoko.digital/

**Source type:** Existing agricultural information and digital market system.

**Key findings:**  
e-HingiriSoko is a Rwandan digital agricultural platform that supports smallholder farmers through market information, market linkages, agricultural services, farmer registration and data collection. Its services also include agricultural extension information, trade and value-chain support.

**Relevance to AgriMonitor Rwanda:**  
This platform demonstrates how digital systems can support agricultural activities and provide useful information to agricultural stakeholders. It provides an example of existing digital innovation within Rwanda's agricultural sector.

**Identified research gap:**  
The platform primarily focuses on agricultural market access, farmer services and value-chain activities. AgriMonitor will have a different focus: storing and analysing crop production, utilisation and post-harvest loss records in an Oracle relational database, with automated identification of high-loss cases.

### 2.5 Dataset: NISR Season B Crop Production

**APA Reference**

National Institute of Statistics of Rwanda. (2026). *Season B: Crop Production* [Dataset]. Rwanda Data Sharing Platform. Retrieved November 13, 2026, from https://data.gov.rw/datasets/eb96d559-71aa-430e-b00c-09da8fbeaf1a

**Source type:** Official government agricultural dataset.

**Key findings:**  
The dataset contains plot-level agricultural production information collected during Season B (March–June 2024) of the 2023/2024 Seasonal Agricultural Survey. It includes crop identification, seed information, harvested quantities, production utilisation and post-harvest losses by different causes.

The dataset covers agricultural plots across Rwanda's provinces and districts. Its variables support analysis of production, household consumption, sales, storage and losses occurring during different agricultural activities.

**Initial dataset inspection:**  
The downloaded CSV file contains 35,584 records and 98 columns. These records provide the actual data to be examined and prepared for the project's Oracle database.

**Relevance to AgriMonitor Rwanda:**  
This dataset is the main data source for the project. It will be used to develop relational tables, load agricultural records and implement PL/SQL procedures, functions, reports and loss-monitoring rules.

**Identified research gap:**  
The dataset provides survey information but does not itself provide the proposed Oracle database application, automated high-loss alert mechanism or project-specific analytical reporting. AgriMonitor will develop these capabilities using the available records.

**Data limitation:**  
The records represent reported agricultural survey observations rather than continuous real-time farm measurements. The system will therefore analyse the available survey data and must not be presented as a live farm-monitoring platform.

### 2.6 Technical Documentation: Oracle DBMS_SCHEDULER

**APA Reference**

Oracle. (2025). *Oracle Database PL/SQL Packages and Types Reference: DBMS_SCHEDULER*. Oracle. https://docs.oracle.com/en/database/oracle/oracle-database/21/arpls/database-pl-sql-packages-and-types-reference.pdf

**Source type:** Official database technical documentation.

**Key findings:**  
Oracle documentation describes DBMS_SCHEDULER as a package that supports the creation, configuration and execution of scheduled database jobs. These jobs can execute PL/SQL blocks or stored procedures according to defined schedules.

**Relevance to AgriMonitor Rwanda:**  
This feature provides the technical foundation for the proposed Smart Post-Harvest Loss Alert System. A scheduled PL/SQL job can periodically execute a procedure that examines recorded loss indicators and stores alerts for cases that meet approved thresholds.

**Identified research gap:**  
Oracle provides general scheduling functionality but does not supply an agricultural post-harvest loss monitoring application. AgriMonitor will apply this database capability to agricultural production and loss analysis.

## 3. Overall Research Findings and Identified Gap

The reviewed research papers establish that maize storage losses and storage technology adoption are important issues among smallholder farmers in Rwanda. The MINAGRI annual report provides national evidence of post-harvest losses at different stages of agricultural production. The e-HingiriSoko platform demonstrates the use of digital technology in Rwanda's agricultural sector, while the NISR dataset provides actual survey records for crop production, utilisation and post-harvest loss analysis.

However, these sources do not provide the specific project solution proposed by AgriMonitor Rwanda: an Oracle relational database application that integrates crop production, utilisation and loss information and uses PL/SQL automation to identify high-loss cases.

The identified project opportunity is therefore to develop a structured agricultural information system that transforms available survey records into organised data, useful analytical outputs and automated loss alerts.

## 4. Proposed Contribution of AgriMonitor Rwanda

Based on the research findings, the project proposes the following contributions:

1. Develop a relational Oracle database for organising agricultural crop production and utilisation records.
2. Store and analyse production information by crop, district and agricultural season where the available data supports it.
3. Analyse reported post-harvest losses by cause and calculate appropriate loss indicators.
4. Develop PL/SQL procedures, functions, packages and cursors for agricultural data processing and reporting.
5. Implement a Smart Post-Harvest Loss Alert System using PL/SQL automation to identify records or groups with high reported loss levels.
6. Provide useful reports to support agricultural analysis and decision-making.

## 5. Conclusion

The reviewed sources demonstrate the relevance of post-harvest loss management in Rwanda and establish a suitable foundation for AgriMonitor Rwanda. The NISR Season B Crop Production dataset provides real agricultural survey records, while Oracle PL/SQL offers the database programming and scheduling capabilities required for the proposed solution.

AgriMonitor Rwanda will contribute by organising agricultural data in a relational database, analysing production and utilisation patterns, and identifying high post-harvest loss cases through automated database processes. The system is intended to support agricultural information analysis and decision-making rather than replace existing national agricultural platforms or provide real-time farm measurements.

## References

Benimana, G. U., Ritho, C., & Irungu, P. (2021). Assessment of factors affecting the decision of smallholder farmers to use alternative maize storage technologies in Gatsibo District-Rwanda. *Heliyon, 7*(10), e08235. https://doi.org/10.1016/j.heliyon.2021.e08235

Benimana, G. U., Ritho, C., & Irungu, P. (2023). Impact of adopting maize hermetic storage technologies on smallholder farmers' income in Gatsibo District, Rwanda. *Heliyon, 9*(3), e14592. https://doi.org/10.1016/j.heliyon.2023.e14592

e-HingiriSoko. (n.d.). *e-HingiriSoko: Digital markets ecosystem platform*. https://ehingirisoko.digital/

Ministry of Agriculture and Animal Resources. (2025). *Annual report 2024–2025*. Government of Rwanda. https://www.minagri.gov.rw/fileadmin/user_upload/Minagri/Publications/Annual_Reports/Annual_report_2024-2025_Final.pdf

National Institute of Statistics of Rwanda. (2026). *Season B: Crop Production* [Dataset]. Rwanda Data Sharing Platform. Retrieved November 13, 2026, from https://data.gov.rw/datasets/eb96d559-71aa-430e-b00c-09da8fbeaf1a

Oracle. (2025). *Oracle Database PL/SQL Packages and Types Reference: DBMS_SCHEDULER*. Oracle. https://docs.oracle.com/en/database/oracle/oracle-database/21/arpls/database-pl-sql-packages-and-types-reference.pdf
