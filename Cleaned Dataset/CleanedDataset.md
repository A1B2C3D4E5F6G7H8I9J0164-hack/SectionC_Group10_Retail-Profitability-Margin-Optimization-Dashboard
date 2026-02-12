# Data Cleaning Documentation

## Dataset

Raw dataset used: `Dataset_Capstone.csv`

This document describes the preprocessing and data cleaning steps applied to create `cleaned.csv`.

---

## 1️⃣ Handling Missing Values

Several columns contained blank or null entries. These were treated using the following strategies:

* **Row ID**

  * Missing values replaced with sequential row numbers

* **Order ID**

  * Missing values replaced with `"MISSING_ID"`

* **Order Date**

  * Blank values replaced with current date
  * Text-formatted dates converted to proper date format

* **Ship Date**

  * Missing values estimated as:

    ```
    Ship Date = Order Date + 3 days
    ```

* **Ship Mode**

  * Missing values replaced with `"Standard Class"`

* **Customer ID**

  * Filled with `"UNKNOWN"`

* **Customer Name**

  * Filled with `"Unknown"`

* **Segment**

  * Default value `"Consumer"`

* **Country**

  * Default value `"United States"`

* **City / State**

  * Missing replaced with `"Unknown"`

* **Postal Code**

  * Missing values filled using column median

* **Region**

  * Default value `"West"`

* **Product ID**

  * Filled with `"UNKNOWN"`

* **Category**

  * Default `"Office Supplies"`

* **Sub Category**

  * Default `"Misc"`

* **Product Name**

  * Missing replaced with `"Unknown Product"`

* **Sales**

  * Missing values replaced using column average

---

## 2️⃣ Text Standardization

To ensure consistency:

* Removed extra spaces using TRIM
* Converted names and locations to proper case
* Standardized categorical entries

---

## 3️⃣ Date Normalization

* Converted numeric serial dates to readable format
* Converted text dates using parsing formulas
* Ensured entire column uses uniform Date format

---

## 4️⃣ Automation

Cleaning was implemented using Google Sheets formulas (`ARRAYFORMULA`) to ensure:

* Reproducibility
* Automatic updates when raw data changes
* Scalable processing

---

## ✅ Result

A structured and cleaned dataset (`cleaned.csv`) ready for:

* Pivot table analysis
* Dashboard visualization
* Business insights generation

---
