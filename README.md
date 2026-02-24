# Instagram Performance Analytics Dashboard (Complete Documentation)

---

# 📌 Project Title

Instagram Performance Analytics Dashboard using Power BI

---

# 🎯 Project Objective

To analyze Instagram performance data and derive actionable insights related to engagement, growth, posting strategy, content effectiveness, and virality using Power BI. The goal was to build an end-to-end business dashboard that converts raw social media data into decision-ready insights.

---

# 🧠 Business Problem

Content creators and brands often struggle with:

* Identifying high-performing content types
* Understanding optimal posting time
* Improving follower growth
* Identifying factors driving virality

This dashboard solves these problems using data-driven analysis and visual storytelling.

---

# 📊 Dataset Overview

Source: Kaggle Instagram Analytics Dataset

The dataset contains post-level performance data including engagement metrics, growth indicators, content metadata, time-based features, and virality classification.

---

# 🛠 Tools Used

* Power BI Desktop
* DAX (Data Analysis Expressions)
* Data visualization and storytelling principles

---

# 🔄 Project Workflow (Start → End)

---

# Step 1 — Data Import

* Imported CSV using Get Data → Text/CSV
* Validated column structure and preview

---

# Step 2 — Data Cleaning (Power Query)

* Converted numeric columns (likes, reach, followers)
* Fixed date and time formats
* Removed nulls and inconsistencies
* Standardized column names

Purpose: Ensure high-quality data before analysis.

---

# Step 3 — Feature Engineering (Calculated Columns)

## 1️⃣ CTA Label

```DAX
CTA Label = IF(Instagram_Analytics[has_call_to_action]=1,"CTA","No CTA")
```

Used for readable comparisons in visuals.

## 2️⃣ Day Type (Weekend vs Weekday)

```DAX
Day Type =
IF(
    Instagram_Analytics[day_of_week] IN {"Saturday","Sunday"},
    "Weekend",
    "Weekday"
)
```

Used for posting strategy analysis.

## 3️⃣ Viral Flag

```DAX
Viral Flag =
IF(
    Instagram_Analytics[performance_bucket_label] = "High",
    "Viral",
    "Non-Viral"
)
```

Used for virality comparisons.

---

# Step 4 — DAX Measures

## 1️⃣ Total Posts

```DAX
Total Posts = DISTINCTCOUNT(Instagram_Analytics[post_id])
```

## 2️⃣ Total Engagement

```DAX
Total Engagement =
SUM(Instagram_Analytics[likes]) +
SUM(Instagram_Analytics[comments]) +
SUM(Instagram_Analytics[shares]) +
SUM(Instagram_Analytics[saves])
```

## 3️⃣ Avg Engagement Rate

```DAX
Avg Engagement Rate = AVERAGE(Instagram_Analytics[engagement_rate])
```

## 4️⃣ Followers Gained Total

```DAX
Followers Gained Total = SUM(Instagram_Analytics[followers_gained])
```

## 5️⃣ Viral Posts %

```DAX
Viral Posts % =
DIVIDE(
    CALCULATE(
        COUNTROWS(Instagram_Analytics),
        Instagram_Analytics[performance_bucket_label] = "High"
    ),
    COUNTROWS(Instagram_Analytics)
)
```

Formatted as percentage.

## 6️⃣ Avg Reach

```DAX
Avg Reach = AVERAGE(Instagram_Analytics[reach])
```

---

# 📊 Dashboard Design Strategy

Built as a single-page executive dashboard with a clear hierarchy:

1. KPIs
2. Engagement insights
3. Growth trends
4. Content intelligence
5. Virality analysis

---

# 📈 VISUALS + BUSINESS INSIGHTS

---

# 🔝 KPI CARDS

Metrics shown:

* Total Accounts
* Total Posts
* Avg Engagement Rate
* Viral Posts %
* Followers Gained
* Avg Reach

### Business Insight

Provides a quick snapshot of overall platform health and growth trajectory.

---

# 📊 Engagement by Media Type

**Visual:** Column chart
**Measure:** Total Engagement

### Insight

Images and carousels generated higher engagement than reels, indicating audience preference for static content formats.

---

# 📊 Engagement by Content Category

**Visual:** Horizontal bar chart
**Measure:** Total Engagement

### Insight

Lifestyle, fashion, and photography categories drove the highest engagement, suggesting niche-specific content optimization opportunities.

---

# 📊 Hashtags vs Reach

**Visual:** Scatter plot
**Fields:** hashtags_count vs reach

### Insight

Posts using 5–8 hashtags achieved the highest reach, while excessive hashtags reduced performance, indicating an optimal hashtag range.

---

# 📊 CTA vs No CTA

**Visual:** Bar chart
**Measure:** Followers Gained Total

### Insight

Posts with a call-to-action drove significantly higher follower growth, highlighting the importance of engagement prompts.

---

# 📈 Follower Growth Trend

**Visual:** Line chart
**Measure:** Followers Gained Total by Year

### Insight

Follower growth showed a consistent upward trend, indicating sustained content performance and audience expansion.

---

# 📊 Engagement by Day of Week

**Visual:** Bar chart
**Measure:** Total Engagement

### Insight

Mid-week posts (especially Tuesday) delivered the highest engagement, suggesting optimal posting windows during weekdays.

---

# 📊 Weekend vs Weekday

**Visual:** Donut chart
**Measure:** Total Engagement

### Insight

Weekday posts accounted for the majority of engagement, indicating professional audience behavior patterns.

---

# 📊 Caption Length vs Engagement

**Visual:** Scatter plot

### Insight

Moderate caption lengths performed better than extremely short or long captions, indicating balance between clarity and storytelling.

---

# 🔥 Virality Distribution

**Visual:** Donut chart
**Field:** performance_bucket_label

### Insight

Posts were fairly distributed across performance buckets, with a small percentage achieving viral status, highlighting the rarity of virality.

---

# 📊 Viral vs Non-Viral Comparison

**Visual:** Bar chart
**Measure:** Avg Engagement Rate

### Insight

Viral posts had significantly higher engagement rates than non-viral posts, validating engagement as a key virality driver.

---

# 📊 Traffic Source → Viral Posts

**Visual:** Stacked bar chart
**Fields:** traffic_source + Viral Flag

### Insight

Explore and hashtag feeds contributed most to viral content discovery, emphasizing algorithm-driven reach.

---

# 💡 Key Business Insights (Summary)

1. Static content (images/carousels) drives higher engagement.
2. Optimal hashtag range is 5–8 tags per post.
3. Call-to-actions significantly improve follower growth.
4. Weekday posting yields higher engagement than weekends.
5. Viral posts are driven by high engagement and discovery feeds.
6. Consistent posting leads to steady audience growth.

---

# 💼 Business Value

This dashboard enables:

* Influencers to optimize posting strategy
* Brands to improve content ROI
* Social media managers to identify high-performing formats
* Marketing teams to understand virality drivers

---

# 🧠 Skills Demonstrated

* Data cleaning and transformation
* DAX calculations
* KPI modeling
* Visual storytelling
* Business insight generation
* Executive dashboard design

---

# 🚀 Future Enhancements

* Predictive virality modeling
* Real-time Instagram API integration
* Multi-page drill-through dashboards
* Automated reporting

---

# 🏁 Conclusion

This project demonstrates end-to-end analytics capability using Power BI, from raw data ingestion to advanced business insights. It highlights proficiency in DAX, data modeling, and storytelling, making it suitable for data analyst and business intelligence roles.

---

# 📌 Author

Sairaju Bathula

Tools: Power BI, DAX
Domain: Social Media Analytics
Project Type: Portfolio Project
