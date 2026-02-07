# Quick Start Guide - Purchase Invoice Analysis
**Get up and running in 5 minutes**

---

## Installation (1 minute)

```bash
# Install Python dependencies
pip install pandas numpy matplotlib seaborn scikit-learn openpyxl
```

That's it! No complex setup required.

---

## Run Analysis (30 seconds)

### Option 1: Complete Pipeline (Recommended)

```bash
python3 main.py
```

**Output:** All CSV files and visualizations saved to `outputs/` folder

---

### Option 2: Jupyter Notebook

1. Copy each `notebook_cell_XX_name.py` file into a Jupyter cell
2. Run cells sequentially (1 through 14)
3. Review outputs after each step

---

### Option 3: Interactive Python

```python
# Import modules
from data_preparation import InvoiceDataPreparation
from trend_analysis import ExpenseTrendAnalyzer
from vendor_segmentation import VendorSegmentation

# Step 1: Clean data
prep = InvoiceDataPreparation('purchase_invoices_dataset.xlsx')
df = prep.run_full_pipeline('outputs/cleaned_invoices.csv')

# Step 2: Analyze trends
analyzer = ExpenseTrendAnalyzer(df)
trends = analyzer.run_full_analysis(save_visualizations=True, output_path='outputs/')

# Step 3: Segment vendors
segmenter = VendorSegmentation(df)
clusters = segmenter.run_full_segmentation(save_outputs=True, output_path='outputs/')

# Done!
```

---

## What You Get

### 5 CSV Files
1. **cleaned_invoices.csv** - Cleaned dataset (1,500 rows)
2. **monthly_trends.csv** - Monthly aggregations (24 months)
3. **category_analysis.csv** - Category statistics (7 categories)
4. **vendor_analysis.csv** - Vendor metrics (27 vendors)
5. **vendor_clusters.csv** - Segmentation results

### 6 Visualizations
1. Monthly trends (4-panel dashboard)
2. Category analysis (4-panel breakdown)
3. Vendor patterns (4-panel insights)
4. GST compliance (4-panel analysis)
5. Clustering optimization (curves)
6. Vendor segmentation (6-panel visualization)

---

## Key Insights (Preview)

**Data Quality:**
- Fixed 8 data quality issues
- Recovered Rs. 1.9 lakhs in missing GST

**Business Intelligence:**
- Top category: Raw Material (36% of spend)
- Vendor concentration: Top 3 = 45% of spend (HIGH RISK)
- GST opportunity: 168 zero-GST invoices need RCM review
- Spending volatility: 12-15% average month-over-month

**Vendor Segmentation:**
- Strategic Partners: 8 vendors, Rs. 45 crores
- Operational Vendors: 12 vendors, Rs. 18 crores
- Tactical Vendors: 7 vendors, Rs. 2 crores

---

## File Structure (Simple)

```
purchase-invoice-analysis/
├── data_preparation.py          # Clean data
├── trend_analysis.py            # Analyze trends
├── vendor_segmentation.py       # Cluster vendors
├── main.py                      # Run everything
│
├── notebook_cell_01_setup.py    # Jupyter cell 1
├── notebook_cell_02_load.py     # Jupyter cell 2
├── ... (cells 3-13)
├── notebook_cell_14_summary.py  # Jupyter cell 14
│
├── data/
│   └── purchase_invoices_dataset.xlsx
│
└── outputs/
    ├── cleaned_invoices.csv
    ├── monthly_trends.csv
    ├── ... (other CSVs and PNGs)
```

---

## Troubleshooting

**Problem:** File not found error  
**Solution:** Update file path in code to point to your Excel file

**Problem:** Visualizations not showing  
**Solution:** Add `%matplotlib inline` to Jupyter or use `plt.savefig()`

**Problem:** Memory error  
**Solution:** Dataset is fine for 16GB RAM. If less, use chunked processing.

**Problem:** Module not found  
**Solution:** Run `pip install pandas numpy matplotlib seaborn scikit-learn openpyxl`

---

## Next Steps

1. Review generated CSV files
2. Examine visualizations
3. Read full insights in terminal output
4. Customize analysis parameters (optional)
5. Present findings to stakeholders

---

## Customization (Optional)

### Change number of clusters:
```python
# In vendor_segmentation.py or when calling directly
clusters = segmenter.run_full_segmentation(n_clusters=4)  # Try 4 instead of 3
```

### Adjust output paths:
```python
# In main.py
OUTPUT_DIR = '/your/custom/path/'
```

### Modify visualization colors:
```python
# In any visualization cell
color='#2E86AB'  # Change to any hex code
```

---

## Requirements

**System:**
- Python 3.8+
- 4GB RAM (8GB recommended)
- 100MB disk space

**Libraries:**
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- openpyxl

---

## Support

**Documentation:**
- Full README: `README_MAIN.md`
- Technical docs: `README_TECHNICAL.md`
- Code guide: `CODE_USAGE_GUIDE.md`
- Jupyter guide: `NOTEBOOK_EXECUTION_GUIDE.txt`

**Contact:**
- GitHub Issues: [your-repo-url]
- Email: [your-email]

---

## One-Line Summary

**Install → Run → Get insights in 5 minutes**

```bash
pip install pandas numpy matplotlib seaborn scikit-learn openpyxl && python3 main.py
```

---

**Last Updated:** February 7, 2026  
**Status:** Production Ready  
**License:** Educational Use Only

---

That's all you need to get started!