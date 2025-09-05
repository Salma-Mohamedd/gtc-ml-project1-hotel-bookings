<p align="center">
  <b>gtc-ml-project1-hotel-bookings</b><br>
  🚀 Data Cleaning & Preprocessing • 🧼📊 → 🤖
</p>

# Hotel Bookings — ML-Ready Dataset 🎯

**Goal:** make hotel_bookings.csv clean, consistent, and ready for machine learning.  
**Highlights:** ✅ EDA ✅ Missingness handling ✅ Outliers ✅ Feature engineering ✅ Encoding ✅ Train/test split

---

## 📦 Repository contents

1. **Notebook** — GTC_ML_Project_1_Data_Cleaning_&_Preprocessing_Challenge.ipynb 
2. **Cleaned Dataset** — cleaned_hotel_bookings.csv
---

## 🧭 Project overview

- **Dataset shape:** 119,390 × 32 
- **Typical target (later phases):** is_canceled (not modeled here; focus is data prep)

---

## ✅ What I did

### Phase 1 — Exploratory Data Analysis (EDA) & Data Quality Report 📊
- Structure & stats
- Missingness: table + **missingno** matrix/heatmap
- Outliers: boxplots + IQR

### Phase 2 — Data Cleaning 🧼
- **Missing values**
  - `agent`: replaced with a flag(0/1) column 'has_agent'
  - `company`: dropped
  - `children`: filled with mode
  - `country`: NA ⇒ filled with mode
- **Outliers**
  - capped adr and lead_times between 0 and their upper limit
- **Duplicates**: dropped
- **Data types**
  - children to int
  - reservation_status_date to datetime
- **Leakage removed**
  - Dropped **reservation_status** & **reservation_status_date**

### Phase 3 — Feature Engineering & Preprocessing 🧠
- **New features**
  - total_guests = adults + children + babies
  - `total_nights = stays_in_weekend_nights + stays_in_week_nights
  - is_family = 1 if (children + babies) > 0 else 0
- **Encoding**
  - One-hot (low-cardinality): meal , market_segment , distribution_channel , deposit_type , customer_type , reserved_room_type , assigned_room_type , hotel 
  - Frequency encoding (High-cardinality): country
- **Split**
  - train_test_split(test_size=0.2, random_state=42)
---
**Developed during my GTC Machine Learning track internship ✨**
