# NYC Airbnb Data Management & Quality Analysis

A data management project focused on data quality assessment, preprocessing, metadata design, and graph-based analysis of the NYC Airbnb 2019 dataset using Python.

## Project Overview

This project applies a complete data management workflow to the NYC Airbnb 2019 dataset, covering:

- Data quality profiling
- Data cleaning and preprocessing
- Metadata creation and FAIR data considerations
- Graph modelling and network analysis
- Gephi-compatible graph export

The dataset contains 48,895 Airbnb listings across 16 attributes, including listing information, host details, neighbourhoods, room types, pricing, reviews, and availability.

## Project Workflow

### 1. Data Quality Profiling

The raw dataset was analysed to identify data-quality issues before preprocessing.

Key findings included:

- 48,895 rows
- 16 columns
- 10,052 missing values in `last_review`
- 10,052 missing values in `reviews_per_month`
- 0 fully duplicated rows
- Unique listing IDs
- Extreme values in `price` and `minimum_nights`

### 2. Data Cleaning & Preprocessing

A Python-based preprocessing workflow was used to improve data consistency and analytical usability.

The workflow included:

- Missing-value handling
- Invalid-value removal
- Data-type conversion
- Date standardization
- Text and categorical standardization
- IQR-based outlier treatment
- One-hot encoding
- Final validation and dataset export

### 3. Metadata & FAIR Data

A metadata file was created using Schema.org-style dataset metadata, including dataset description, source information, variables, spatial coverage, temporal coverage, and licensing information.

### 4. Graph Modelling & Network Analysis

A property graph was created using NetworkX to represent relationships among:

- Hosts
- Listings
- Neighbourhoods
- Neighbourhood groups
- Room types

The graph was exported in GEXF and GraphML formats for use with Gephi.

The current full-graph execution generated:

- **81,501 nodes**
- **137,916 edges**

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- NetworkX
- Matplotlib
- Seaborn
- Jupyter Notebook
- Gephi

## Repository Structure

nyc-airbnb-data-management/
│
├── Airbnb/
│   ├── AB_NYC_2019_Cleaned_Final.csv
│   ├── AB_NYC_2019_Encoded.csv
│   └── Airbnb_NYC_2019_RAW.csv
│
├── graph/
│   ├── gephi_exports/
│   │   ├── airbnb_property_graph_FULL.gexf
│   │   └── airbnb_property_graph_FULL.graphml
│   │
│   └── samples/
│       ├── airbnb_property_graph_sample.gexf
│       └── airbnb_property_graph_sample.graphml
│
├── metadata/
│   └── dataset_metadata.json
│
└── notebooks/
    ├── 01_data_quality_profiling.ipynb
    ├── 02_data_cleaning_preprocessing.ipynb
    └── 03_graph_modelling_network_analysis.ipynb
    
## Dataset
The project uses the New York City Airbnb Open Data 2019 dataset.
Source:
https://www.kaggle.com/dgomonov/new-york-city-airbnb-open-data
The raw dataset is expected at:
Airbnb/Airbnb_NYC_2019_RAW.csv