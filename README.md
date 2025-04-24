# 🔍 MS Power BI Measure Extractor

> *Extract all used measures, their names, and data sources within your Power BI Reports.*

## 📋 What This Tool Does

This Python script extracts all measures used in your Power BI reports and organizes them in a clean, tabular format:

| Report Name | Report Page | Visualisation | Name Measure | Data Source |
| ------------ | ------------ | -------------- | ------------ | ----------- |
| Report Name | Page 1 | Chart Name | Measure Name | #_Measure.Example |

## 🚀 Why You Need This

- **Audit your reports** - Quickly identify all measures across multiple reports
- **Documentation** - Create comprehensive documentation of your Power BI environment
- **Dependency tracking** - Understand which measures are used where
- **Governance** - Support your data governance initiatives with clear measure lineage

## 🛠️ Prerequisites

Before running this code, make sure you have:

1. **Python installed** (3.6 or higher recommended)
2. **Required libraries**:
   - pandas
   - json
   - zipfile
   - os
   - datetime

## 📝 How to Use

1. **Place your .pbix files** in the same directory as this script
   - ⚠️ *Note: Every .pbix file in the folder will be processed*

2. **Run the script** through:
   - Jupyter Notebook

3. **Check the output**:
   - A CSV file named `Extract_PBI_Measures_YYYYMMDD_HHMMSS.csv` will be created
   - The file is encoded in UTF-16 to support special characters

## 🔧 How It Works

The script performs these operations:

1. **Scans the current directory** for .pbix files
2. **Unzips each file** to access the internal JSON structure
3. **Parses the Report/Layout** section to extract:
   - Report names
   - Page names
   - Visualization titles
   - Measure names
   - Data sources
4. **Filters out slicers and textboxes** (which don't contain measures)
5. **Compiles everything** into a pandas DataFrame
6. **Exports to CSV** with a timestamp in the filename

## 💡 Tips for Best Results

- Run this on a folder containing only the .pbix files you want to analyze
- For large reports, be patient as extraction may take a few moments
- The resulting CSV can be imported into Excel or Power BI for further analysis

## ⚠️ Limitations

- The script only extracts measures from visualizations, not from calculated columns or tables
- Some complex custom visuals might not have their measures properly extracted
- The script doesn't extract DAX formulas, only measure names and references

---

*Happy analyzing!*
