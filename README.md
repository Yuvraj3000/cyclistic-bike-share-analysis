# Cyclistic Bike-Share: Member vs Casual Rider Analysis

> A data analytics case study analyzing 5.6 million bike-share trips to uncover behavioral differences between casual riders and annual members — and recommend strategies to drive membership conversion.

> **Capstone Project — Google Data Analytics Professional Certificate**

---

## Project Snapshot

| Metric | Value |
|--------|-------|
| Total Trips Analyzed | 4.59 Million (post-cleaning) |
| Casual Riders | 2,048,302 |
| Annual Members | 2,539,802 |
| Data Period | Full Year 2021 |
| Tool Used | R (tidyverse, ggplot2, geosphere, lubridate) |

---

## Business Goal

Cyclistic's finance analysts have determined that annual members are significantly more profitable than casual riders. The marketing team wants to convert existing casual riders into annual members.

**The core question:** *How do annual members and casual riders use Cyclistic bikes differently?*

---

## Dataset

**Source:** [Divvy Trip Data](https://divvy-tripdata.s3.amazonaws.com/index.html)

- 12 months of historical trip data (2021)
- 5,595,063 raw records across 13 columns
- Key fields: `ride_id`, `rideable_type`, `started_at`, `ended_at`, `start_station_name`, `end_station_name`, `start_lat`, `start_lng`, `end_lat`, `end_lng`, `member_casual`

---

## Data Cleaning

Performed in R using `tidyverse` and `janitor`:

- Replaced blank cells with `NA` and removed all incomplete rows
- Converted `started_at` and `ended_at` to `POSIXct` datetime format
- Calculated `duration_sec` and `duration_hr` columns
- Removed negative and zero duration trips (data entry errors)
- Separated datetime into `start_date`, `start_time`, `end_date`, `end_time`
- Calculated geographic distance using `geosphere::distm()`

**Post-cleaning dataset: 4,588,104 rows**

---

## Analysis Tasks & Key Findings

### 1. Total Users
| User Type | Count |
|-----------|-------|
| Casual | 2,048,302 |
| Member | 2,539,802 |

Casuals are approximately 20% fewer than members — a significant untapped conversion opportunity.

---

### 2. Average Ride Time
| User Type | Avg Ride Time (hrs) |
|-----------|---------------------|
| Casual | 1.35 |
| Member | 0.55 |

Casuals ride nearly **2.5x longer** per trip than members — consistent with leisure usage patterns.

---

### 3. Average Distance Traveled
| User Type | Avg Distance (km) |
|-----------|-------------------|
| Casual | 2.18 |
| Member | 2.09 |

Distance is nearly equal — but casuals ride longer durations for similar distances, suggesting slower, more exploratory rides.

---

### 4. Daily Usage Pattern
- **Weekdays:** Members significantly outnumber casuals
- **Weekends:** Casual riders **surpass** members — consistent with leisure behavior
- Members show a clear weekday commute pattern; casuals spike on Saturday/Sunday

---

### 5. Top Boarding Stations (Casuals)
| Rank | Station |
|------|---------|
| 1 | Streeter Dr & Grand Ave |
| 2 | Millennium Park |
| 3 | Michigan Ave & Oak St |
| 4 | Theater on the Lake |
| 5 | Shedd Aquarium |

Top casual stations are all **tourist/leisure destinations** — confirming the leisure hypothesis.

---

### 6. Multi-Day Riders
| User Type | Same Day Return | Multi-Day |
|-----------|----------------|-----------|
| Casual | 2,041,039 | 7,263 |
| Member | 2,536,066 | 3,736 |

Casuals keeping bikes overnight are **nearly double** that of members — suggesting trip/sightseeing usage.

---

### 7. Monthly Trends
- Both groups peak in **July** and dip in **February**
- Casuals drop sharply in winter months — reinforcing leisure/seasonal usage
- Members remain more consistent year-round — commute dependency

---

### 8. Hourly Usage Pattern
- **Members** show clear peaks at commute hours: 8AM and 5PM
- **Casuals** show a steady daytime rise peaking around 5PM
- Casuals outnumber members late at night — possible night shift workers

---

## Key Insight: Casual Rider Segments

The analysis reveals casuals are **not a homogeneous group**. Three distinct sub-segments exist:

1. **Leisure riders** — weekend tourists and city explorers (majority)
2. **College/student commuters** — morning usage spike at specific stations
3. **Night shift workers** — elevated late-night casual usage

---

## Recommendations

### 1. Weekend & Holiday Membership Discounts
Offer targeted discounts during weekends when casual ridership peaks. A weekend-specific membership tier could be an entry point for conversion.

### 2. Dynamic Pricing Strategy
Introduce member-only pricing benefits during the 1PM–5PM peak window — when casuals are most active — to incentivize membership at the exact moment they feel the need.

### 3. Student Membership Program
Offer discounted memberships for students with college ID verification. Target advertising near top casual boarding stations and university areas.

### 4. Station-Level Advertising
Place conversion-focused ads at the top 10 casual boarding stations — Streeter Dr, Millennium Park, Michigan Ave & Oak St, Shedd Aquarium, Theater on the Lake.

### 5. Trip & Tourism Positioning
Create marketing content highlighting how Cyclistic membership makes city exploration and trips more affordable — targeting the sightseeing casual segment.

### 6. Night Shift Worker Outreach
Offer nighttime membership discounts or dedicated night-rider plans to capture the late-night casual segment.

---

## Tools & Libraries Used

| Tool / Library | Purpose |
|---------------|---------|
| R | Core analysis language |
| tidyverse | Data manipulation and visualization |
| ggplot2 | All chart visualizations |
| geosphere | Geographic distance calculation |
| lubridate | Date and time manipulation |
| janitor | Data cleaning |
| dplyr | Data wrangling |

---

## How to Run

1. **Download dataset** from [Divvy Trip Data](https://divvy-tripdata.s3.amazonaws.com/index.html) — 2021 monthly files
2. **Install required R packages:**
```r
install.packages(c("tidyverse", "geosphere", "lubridate", "janitor", "ggplot2", "dplyr"))
```
3. **Update file path** in the import section to your local data directory
4. **Run the script** sequentially — each section builds on the previous

---

## Limitations

- Dataset is limited to 2021 — seasonal patterns may vary year to year
- No demographic data available — cannot segment by age, gender, or income
- Geographic distance calculated as straight-line (Haversine) — actual route distance may differ
- Casual riders may include tourists who will never convert regardless of strategy

---

## Author

**Yuvraj**

[![Gmail](https://img.shields.io/badge/Gmail-yuvipahari%40gmail.com-red?style=flat&logo=gmail)](mailto:yuvipahari@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-yuvraj2000-blue?style=flat&logo=linkedin)](https://linkedin.com/in/yuvraj2000)
[![GitHub](https://img.shields.io/badge/GitHub-Yuvraj3000-black?style=flat&logo=github)](https://github.com/Yuvraj3000)

---

*Google Data Analytics Professional Certificate — Capstone Project*
