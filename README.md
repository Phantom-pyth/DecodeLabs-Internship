Sales Transaction Analysis Decode Lab Internship
3week endtoend data analytics project covering data cleaning, exploratory analysis, business trend discovery, and machine learning prediction on a realworld sales dataset.

## Project Overview

This project analyses 1,200 sales transaction records across 14 features using Python. Conducted over three weeks as part of the Decode Lab Data Analytics Internship, it progresses from raw data inspection through to a deployed Linear Regression model predicting order value with R² = 0.89.

Repository Structure

Dataset_for_Data_Analytics.xlsx    Original raw dataset


Sales_Cleaned.csv                 Cleaned & featureengineered dataset


Decode_Lab_Week_1.ipynb            # Data loading, inspection & cleaning


Decode_Lab_Week_2.ipynb            # EDA, trends & visualisations


Decode_Lab_Week_3.ipynb            # ML model, advanced analysis & insights



Sales_Insight_Report.docx          # Full insight summary report (all 3 weeks)


README.md                          # This file

## Dataset Description

Source Dataset_for_Data_Analytics.xlsx 

Rows 1,200 

Columns 14 

Target Variable  TotalPrice 


Date Range  January 2023 – June 2025 

Missing Values CouponCode — 309 (25.75%) 


Duplicates  0 

### Features
FEATURE	TYPE	DESCRIPTION
OrderID	Identifier	Unique order reference
Date	Datetime	Order date
CustomerID	Identifier	Customer reference
Product	Categorical	 7 product types
Quantity	Numeric	Units ordered (1–5)
UnitPrice	Numeric	Price per unit (£11.39–£699.93)
ShippingAddress	Identifier	Delivery address
PaymentMethod	Categorical	5 payment types
OrderStatus	Categorical	5 statuses (Delivered, Shipped, Pending, Cancelled, Returned)
TrackingNumber	Identifier	Shipment tracking reference
ItemsInCart	Numeric	Number of items browsed (1–10)
CouponCode	Categorical	Promotional code used (3 types + None)
ReferralSource	Categorical	Customer acquisition channel
TotalPrice	Numeric	Target


## Weekly Breakdown
### Week 1 Data Loading, Inspection & Cleaning
 Loaded dataset, inspected structure, identified missing values and types
 Imputed CouponCode nulls with "No Coupon" label (preserves all 1,200 rows)
 Converted Date to datetime; extracted Month, Year, Month_num
 IQRbased outlier detection 8 outliers identified and retained (legitimate bulk orders)
 Key finding: UnitPrice (r=0.72) and Quantity (r=0.62) are the dominant TotalPrice predictors

### Week 2 xploratory Data Analysis & Business Trends
 Univariate analysis on all features; bar charts, pie charts, histograms
 Product revenue ranking, payment method distribution, referral source analysis
 Order status breakdown  identified 41.4% cancellation + return rate
 Coupon usage analysis  FREESHIP leads over discountbased codes
 Key finding: Chair and Printer dominate revenue; 41% loss rate is the #1 business risk

### Week 3 — Machine Learning & Advanced Analysis
 Linear Regression model: Quantity, UnitPrice, ItemsInCart → TotalPrice
 R² = 0.89  MAE = £211.53 productiongrade accuracy
 Monthly revenue trend analysis  volatile, no clear seasonality
 TotalPrice by order status  cancellations affect all price tiers equally
 Average order value by referral source  all channels deliver equal customer quality
 Key finding: Model is deployable for realtime price estimation and revenue forecasting

## Key Insights


 1  UnitPrice is the strongest revenue driver  r = 0.72 with TotalPrice 
 2  Chair & Printer dominate product revenue  ~£195K each vs £152K for Phone 
 3  41.4% cancellation + return rate is the biggest business risk  497 of 1,200 orders 
 4  FREESHIP outperforms discount codes as a conversion tool  313 redemptions vs 292, 286 
 5  Instagram is the top acquisition channel by volume  259 orders vs 222 (lowest) 
 6  Quantity cap at 5 creates a hard revenue ceiling per transaction  Max Qty = 5 across all orders 
 7  ML model (R²=0.89) is ready for operational deployment  MAE = £211.53 


## Technologies Used

 Python 3.x
 Pandas  data loading, cleaning, manipulation
 NumPy  numerical operations
 Matplotlib  visualisations
 Scikitlearn  Linear Regression, train/test split, model evaluation
 Jupyter Notebook  interactive analysis environment



## Getting Started

### Prerequisites

bash
pip install pandas numpy matplotlib scikitlearn openpyxl jupyter

### Run the Analysis
bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/salestransactionanalysis.gi](https://github.com/Phantom-pyth/DecodeLabs-Internship.git
cd DecodeLabs-Internship

# Run notebooks in order
jupyter notebook Decode_Lab_Week_1.ipynb
jupyter notebook Decode_Lab_Week_2.ipynb
jupyter notebook Decode_Lab_Week_3.ipynb


## ML Model Summary

Target:   TotalPrice
Features: Quantity, UnitPrice, ItemsInCart
Model:    Linear Regression
Split:    80% train / 20% test (random_state=42)

Performance:
  R² Score:  0.8905
  MAE:       £211.53

Coefficients:
  Quantity     ~350.0   (dominant positive driver)
  UnitPrice    ~2.93    (strong positive driver)
  ItemsInCart  ~1.52   (slight negative — browsing ≠ revenue)

Formula: TotalPrice ≈ 350×Qty + 2.93×UnitPrice − 1.52×ItemsInCart + intercept
## Outputs

 File  Description 

 Sales_Cleaned.csv  Clean dataset with imputed CouponCode and engineered date features 
 Decode_Lab_Week_1.ipynb  Data inspection, cleaning, outlier detection 
 Decode_Lab_Week_2.ipynb  Full EDA with product, payment, referral, and coupon analysis 
 Decode_Lab_Week_3.ipynb  ML model, residual analysis, monthly trends, consolidated insights 
 Sales_Insight_Report.docx  Professional report with 7 business insights and recommendations 

## Contributing
Pull requests are welcome. For major changes, open an issue first.
