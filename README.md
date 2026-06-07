# Quantium-Virtual-Internship---Retail-Strategy-and-Analytics---Task-1

### Overview
This project is Task 1 of the Quantium Virtual Internship on Forage. The goal is to analyse chip purchasing behaviour across customer segments to generate actionable insights for a retail category manager.

The analysis covers:

Data cleaning and quality checks on transaction and customer data

Feature engineering (pack size, brand extraction)

Customer segmentation analysis by lifestage and premium tier

Statistical testing to validate key findings

### Datasets

Dataset  ---   Rows  ---   Columns  ---   Description

QVI_transaction_data.xlsx  ---    264,836 ---    8   ---   Transaction records including date, store, product, quantity, sales

QVI_purchase_behaviour.csv   --- 72,637   ---    3      ---   Customer loyalty card mapped to lifestage and premium tier

 ### Data Cleaning Steps

1. Duplicate removal — 1 duplicate transaction identified and dropped

2. Date conversion — Excel integer dates converted to proper datetime format (origin: 30 Dec 1899)

3.  Salsa filter — Non-chip products containing "salsa" removed from the dataset

4. Outlier removal — Loyalty card 226000 excluded; customer purchased 200 packets twice, likely commercial rather than retail behaviour

5. Brand name standardisation — Fragmented brand labels consolidated (e.g. RED → RRD, SMITH → SMITHS, GRAIN → GRNWVES)

### Feature Engineering

Feature    ----   Method   ---   Example     

PACK_SIZE   ---   Regex extraction of numeric value from product name     -----175, 330, 380

BRAND    ----   First word of product name, uppercased   ----  KETTLE, SMITHS, DORITOS

Pack size range: 70g (smallest) → 380g (largest)

Most common pack size: 175g (66,389 transactions)

 ###  Key Findings

🏆 Top Sales Segments

Sales are primarily driven by three segments:

Budget – Older Families

Mainstream – Young Singles/Couples

Mainstream – Retirees

👥 Customer Volume vs. Spend

Higher sales in the Mainstream–Young Singles/Couples and Mainstream–Retirees segments are largely explained by greater customer volume, not higher individual spend.

Budget–Older Families is a notable exception — high sales despite relatively fewer customers, driven by higher average units per customer.

💰 Price Per Unit

Mainstream midage and young singles/couples pay significantly more per packet than their Budget or Premium counterparts.

Hypothesis: Premium customers may prefer healthier snacks; when they do buy chips it is for entertainment, not personal consumption.

###   📉 Visualisations
Chart     ----     Insight

Transactions over time    -----        Seasonal spike leading up to Christmas; zero sales on Dec 25

Total sales by segment  -----        Budget–Older Families and Mainstream segments dominate

Customers by segment     ----    Mainstream–Young Singles/Couples largest group

Avg units per customer    -----      Older and Young Families buy the most chips per customer

Avg price per unit    -----        Mainstream midage/young singles pay a premium per packet

### 🛠️ Technologies Used

Python 

pandas — data manipulation

numpy — numerical operations

matplotlib — visualisation

scipy.stats — statistical testing

re — regex for feature extraction


### 📜 License

This project was completed as part of the Quantium Data Analytics Virtual Internship on Forage. Dataset rights belong to Quantium.
