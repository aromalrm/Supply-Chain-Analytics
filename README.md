# Supply Chain Analytics

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)

An exploratory supply-chain analysis of orders, shipments, inventory, and warehouse fulfillment. The project prepares operational data for answering questions about delivery performance, inventory efficiency, profitability, and product demand.

<p align="center">
  <img src="data/JIT_Logo.PNG" alt="Just In Time project logo" width="220" />
</p>

## Project objectives

- Assess the quality of order, shipment, inventory, and fulfillment data.
- Prepare consistent fields for reliable operational analysis.
- Measure order-processing and shipment performance.
- Compare product demand with warehouse inventory.
- Identify products, categories, and departments that affect profit or storage cost.
- Create an analysis-ready foundation for dashboards and business recommendations.

## Dataset

The repository includes three CSV files:

| File | Rows | Columns | Purpose |
| --- | ---: | ---: | --- |
| `Orders_and_shipments.csv` | 30,871 | 24 | Orders, customers, products, sales, discounts, profit, and shipment details |
| `Inventory.csv` | 4,200 | 4 | Monthly warehouse inventory and inventory cost per unit |
| `Fulfillment.csv` | 118 | 2 | Product-level warehouse fulfillment time |

Together, the datasets cover customer markets, product hierarchy, warehouse locations, shipment modes, scheduled shipment time, sales, discounts, profit, inventory, and fulfillment duration.

## Analysis workflow

The notebook currently performs the following preparation steps:

1. Loads all three datasets with pandas.
2. Profiles missing values, duplicate rows, schemas, and data types.
3. Normalizes column names by removing unwanted whitespace.
4. Cleans placeholder values in the discount field and converts it to a numeric type.
5. Builds complete order and shipment datetime fields.
6. Standardizes inconsistent country names and special characters.
7. Calculates order-processing time from order to shipment.

The prepared data can then support analysis in four business areas:

- **Business performance:** gross sales, profit, margin, and high-performing products.
- **Inventory management:** supply versus demand, excess inventory, shortages, and storage cost.
- **Shipment performance:** processing time, scheduled shipment time, shipment mode, and regional delays.
- **Fulfillment:** warehouse fulfillment duration by product and category.

## Repository structure

```text
Supply-Chain-Analytics/
├── data/
│   ├── Fulfillment.csv
│   ├── Inventory.csv
│   ├── JIT_Logo.PNG
│   └── Orders_and_shipments.csv
├── Supply_chain_analytics.ipynb
└── README.md
```

## Getting started

### 1. Clone the repository

```bash
git clone https://github.com/aromalrm/Supply-Chain-Analytics.git
cd Supply-Chain-Analytics
```

### 2. Create an environment and install dependencies

```bash
python -m venv .venv
```

Activate the environment and install the packages used by the notebook:

```bash
pip install jupyter pandas numpy
```

### 3. Run the analysis

```bash
jupyter notebook Supply_chain_analytics.ipynb
```

The notebook expects the CSV files to remain inside the `data` directory.

## Key questions this project supports

- Which products and departments generate the strongest profit?
- Where does available inventory fall below product demand?
- Which products create unnecessary inventory carrying costs?
- Which markets, regions, or shipment modes experience longer processing times?
- Which products require the most warehouse fulfillment time?

## Current scope

This repository contains the source datasets and the Python data-preparation notebook. Dashboard files and production data pipelines are outside the current scope. Dataset findings should be treated as portfolio analysis rather than real-time operational reporting.
