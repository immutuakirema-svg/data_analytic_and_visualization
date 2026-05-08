# 🎬 Netflix Titles Dataset

> A comprehensive dataset of Movies and TV Shows available on Netflix, used for exploratory data analysis and visualization.

---

## 📌 Overview

This dataset contains metadata for **8,807 titles** (Movies and TV Shows) available on the Netflix streaming platform. It covers content spanning nearly a century of releases — from **1925 to 2021** — across multiple countries, genres, and content ratings. The dataset is well-suited for trend analysis, content strategy insights, and audience segmentation studies.

---

## 📁 File Information

| Property        | Details                        |
|-----------------|--------------------------------|
| **File Name**   | `netflix_titles.csv`           |
| **Format**      | CSV (Comma-Separated Values)   |
| **Total Rows**  | 8,807                          |
| **Total Columns** | 12                           |
| **File Encoding** | UTF-8                        |

---

## 🗂️ Schema / Column Descriptions

| Column         | Data Type | Description                                                                 | Null Count |
|----------------|-----------|-----------------------------------------------------------------------------|------------|
| `show_id`      | String    | Unique identifier for each title (e.g., `s1`, `s2`)                        | 0          |
| `type`         | String    | Content type — either `Movie` or `TV Show`                                  | 0          |
| `title`        | String    | Name of the movie or TV show                                                | 0          |
| `director`     | String    | Director(s) of the title                                                    | 2,634 ⚠️   |
| `cast`         | String    | Main cast members (comma-separated)                                         | 825        |
| `country`      | String    | Country or countries where the content was produced                         | 831        |
| `date_added`   | String    | Date the title was added to Netflix (e.g., `September 25, 2021`)           | 10         |
| `release_year` | Integer   | The year the title was originally released                                  | 0          |
| `rating`       | String    | Content rating (e.g., `TV-MA`, `PG-13`, `R`)                               | 4          |
| `duration`     | String    | Duration — minutes for Movies, number of seasons for TV Shows               | 3          |
| `listed_in`    | String    | Genre categories the title belongs to (comma-separated)                     | 0          |
| `description`  | String    | Brief synopsis of the title                                                 | 0          |

> ⚠️ The `director` column has the highest missing value count (2,634 rows), likely due to TV Shows that don't attribute a single director.

---

## 📊 Dataset Highlights

### Content Type Distribution
| Type     | Count | Percentage |
|----------|-------|------------|
| Movie    | 6,131 | ~69.6%     |
| TV Show  | 2,676 | ~30.4%     |

### Top Content Ratings
| Rating | Count |
|--------|-------|
| TV-MA  | 3,207 |
| TV-14  | 2,160 |
| TV-PG  | 863   |
| R      | 799   |
| PG-13  | 490   |

### Top Producing Countries
| Country        | Titles |
|----------------|--------|
| United States  | 2,818  |
| India          | 972    |
| United Kingdom | 419    |
| Japan          | 245    |
| South Korea    | 199    |

### Release Year Range
- **Earliest:** 1925
- **Latest:** 2021

---

## 🔍 Data Quality Notes

| Issue                          | Details                                                                 |
|-------------------------------|-------------------------------------------------------------------------|
| Missing directors              | 2,634 rows — common for TV Shows with multiple or uncredited directors  |
| Missing cast                   | 825 rows — some documentary/short form content lacks cast listings      |
| Missing country                | 831 rows — possible for co-productions or unlisted origins              |
| Missing rating                 | 4 rows — minor; can be imputed or dropped                               |
| `date_added` format            | Stored as string — requires parsing before time-series analysis         |
| `duration` mixed format        | `"90 min"` for Movies vs `"2 Seasons"` for TV Shows — needs splitting   |
| `listed_in` / `cast` / `country` | Multi-value fields — require splitting for granular analysis          |

---

## 🧪 Suggested Analysis & Visualizations

The following analyses can be performed on this dataset:

- **Content Growth Over Time** — Trend of titles added to Netflix year by year
- **Movies vs TV Shows Split** — Pie/bar chart of content type distribution
- **Top Genres** — Frequency analysis of `listed_in` categories after splitting
- **Country-wise Content Distribution** — Choropleth map of production countries
- **Rating Distribution** — Bar chart of content ratings (audience suitability)
- **Release Decade Analysis** — Grouping titles by decade to identify content era trends
- **Top Directors & Cast** — Most frequently appearing directors and actors
- **Duration Analysis** — Average movie length and most common season counts for shows
- **Content Added by Month/Year** — Time-series of Netflix library growth

---

## 🛠️ Recommended Libraries

```python
import pandas as pd          # Data loading and manipulation
import numpy as np           # Numerical operations
import matplotlib.pyplot as plt  # Basic visualizations
import seaborn as sns        # Statistical visualizations

```

---

## 🚀 Quick Start

```python
import pandas as pd

# Load the dataset
df = pd.read_csv('netflix_titles.csv')

# Basic info
print(df.shape)        # (8807, 12)
print(df.dtypes)
print(df.isnull().sum())

# Preview
df.head()
```

---

## 📜 Data Source

This dataset is sourced from **Kaggle's Netflix Movies and TV Shows** dataset, originally compiled from Netflix's publicly available catalog data.

> **Note:** The dataset reflects Netflix content as of a specific snapshot (up to late 2021) and may not represent the current Netflix library.

---

## 📄 License

This dataset is intended for **educational and analytical purposes only**. All content titles, descriptions, and associated metadata are the property of Netflix and their respective rights holders.
