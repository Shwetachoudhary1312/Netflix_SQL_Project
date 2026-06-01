# 🎬 Netflix Content Analysis — SQL Project

A comprehensive SQL-based analysis of Netflix's content library using PostgreSQL — answering 15 business questions around content distribution, ratings, genres, and regional trends across 8,000+ titles.

---

## 📌 Project Overview

This project explores what Netflix's content catalog actually looks like under the hood. Using advanced SQL techniques on a real dataset, I answered questions a content strategy or data team at a streaming platform would genuinely care about — from rating distributions to regional content gaps.

**Goals:**
- Understand the split between Movies vs TV Shows
- Identify content trends by country, year, and genre
- Analyse ratings, durations, and director/actor patterns
- Categorize content by keywords for content moderation insights

---

## 🗄️ Database Schema

```sql
CREATE TABLE netflix (
    show_id      VARCHAR(5),
    type         VARCHAR(10),
    title        VARCHAR(250),
    director     VARCHAR(550),
    casts        VARCHAR(1050),
    country      VARCHAR(550),
    date_added   VARCHAR(55),
    release_year INT,
    rating       VARCHAR(15),
    duration     VARCHAR(15),
    listed_in    VARCHAR(250),
    description  VARCHAR(550)
);
```

---

## ❓ Business Problems Solved (15 Queries)

| # | Business Question | SQL Concept Used |
|---|---|---|
| 1 | Movies vs TV Shows count | GROUP BY, COUNT |
| 2 | Most common rating per content type | CTE, RANK(), Window Function |
| 3 | All movies from a specific year | WHERE filter |
| 4 | Top 5 countries by content volume | UNNEST, STRING_TO_ARRAY |
| 5 | Longest movie on Netflix | SPLIT_PART, ORDER BY |
| 6 | Content added in last 5 years | TO_DATE, INTERVAL |
| 7 | All content by director 'Rajiv Chilaka' | Subquery, UNNEST |
| 8 | TV Shows with more than 5 seasons | SPLIT_PART, type cast |
| 9 | Content count by genre | UNNEST, GROUP BY |
| 10 | Top 5 years by India content release avg | Subquery, ROUND, percentage calc |
| 11 | All documentary movies | LIKE filter |
| 12 | Content with no director | IS NULL |
| 13 | Salman Khan movies in last 10 years | LIKE, EXTRACT(YEAR) |
| 14 | Top 10 actors in Indian content | UNNEST, COUNT, ORDER BY |
| 15 | Content categorized by 'kill'/'violence' | CASE WHEN, ILIKE |

---

## 💡 Key Findings

- **Movies dominate** Netflix's catalog — roughly 70% movies vs 30% TV shows
- **TV-MA** is the most common rating, indicating Netflix skews toward adult audiences
- **USA and India** are the top two content-producing countries on the platform
- **India's content releases peaked** around 2017–2019 before leveling off
- **Dramas and Comedies** are the most represented genres across both movies and shows
- **2,600+ titles** have no director listed — a data quality gap worth flagging
- Content flagged with violence/kill keywords accounts for a notable share — relevant for parental controls and content tagging

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| PostgreSQL | Database and query execution |
| pgAdmin | SQL IDE |
| Kaggle | Dataset source |

---

## 📂 Files in this Repo

```
Netflix_SQL_Project/
│
├── netflix_titles.csv              # Raw dataset (8,000+ titles)
├── Schemas.sql                     # Table creation script
├── Business Problems Netflix.sql   # All 15 business queries
└── README.md
```

---

## 🚀 How to Run

```sql
-- 1. Create the table
\i Schemas.sql

-- 2. Load data (via pgAdmin import or COPY command)
COPY netflix FROM '/path/to/netflix_titles.csv' DELIMITER ',' CSV HEADER;

-- 3. Run queries
\i 'Business Problems Netflix.sql'
```

---

## 📈 Future Enhancements

- [ ] Add a Python EDA layer with visualizations using Matplotlib/Seaborn
- [ ] Build a Power BI dashboard on top of the SQL analysis
- [ ] Extend with IMDb ratings data for deeper content quality analysis

---

## 🙋‍♀️ About Me

**Shweta Choudhary** — Data Analyst | BIT Mesra, AIML (2026)

I enjoy finding patterns in data that tell a story — whether it's what people watch or what they buy.

📧 shwetachoudhary1312@gmail.com
🔗 [LinkedIn](https://linkedin.com/in/your-profile) | [GitHub](https://github.com/Shwetachoudhary1312)

---

*Dataset: [Netflix Movies and TV Shows — Kaggle](https://www.kaggle.com/datasets/shivamb/netflix-shows)*


