# Dataset Documentation – AgriMonitor Rwanda

## 1. Dataset Title
Season B: Crop Production (2023/2024)

## 2. Data Source
National Institute of Statistics of Rwanda (NISR), Rwanda Data Sharing Platform.

Dataset link: https://data.gov.rw/datasets/eb96d559-71aa-430e-b00c-09da8fbeaf1a

## 3. Dataset Description
The dataset contains agricultural survey information about crop production, harvest utilisation and post-harvest losses in Rwanda.

The downloaded CSV file contains **35,584 records and 98 columns**.

## 4. Geographic and Time Coverage
- Country: Rwanda
- Coverage: 5 provinces and 30 districts
- Agricultural season: Season B, 2023/2024
- Period: March–June 2024

## 5. Main Information Available
The dataset includes information about:
- Districts and provinces
- Crop names and crop categories
- Plot area and harvested quantities
- Harvest utilisation, including sales, consumption and storage
- Post-harvest losses and reported causes, such as pests, theft, harvesting, transportation and storage

## 6. Purpose of Using the Dataset
The dataset will be used to develop AgriMonitor Rwanda, an Oracle database system for organising and analysing crop production, harvest utilisation and post-harvest losses.

It will support reports by crop, district and loss cause, as well as the identification of records meeting defined high-loss criteria.

## 7. Data Preparation
Before loading the data into the Oracle database, the project will:
- Inspect column names, data types and missing values.
- Check for duplicate records.
- Verify measurement units and relevant quantity definitions.
- Identify fields needed for the project.
- Exclude unnecessary farmer identifiers and other potentially identifying information.
- Prepare the selected data for staging and normalisation.

## 8. Dataset Limitations
The dataset represents historical survey information, not live farm data. Some fields contain missing values, which will be investigated before deciding how to handle them. Loss calculations and alert thresholds will be defined only after checking the relevant variables and their measurement units.

## 9. Reference
National Institute of Statistics of Rwanda. (2026). *Season B: Crop Production* [Dataset]. Rwanda Data Sharing Platform. Retrieved November 13, 2026, from https://data.gov.rw/datasets/eb96d559-71aa-430e-b00c-09da8fbeaf1a
