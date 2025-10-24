**Power BI Workload Coverage Dashboard**

**Project Introduction**

This Power BI dashboard visualizes workload coverage trends using the dataset `work_load_data.csv`.
It is a full analytical recreation of the “Priority Coverage Information” report originally generated in Python.
The dashboard highlights how workload distribution changes by day, hour, and workload priority, providing deep insights into operational performance and resource utilization.

**Dataset Overview**

| Column       | Description                                                                     |
| ------------ | ------------------------------------------------------------------------------- |
| date         | Calendar date of workload record                                                |
| hour         | Hour of the day (0–23)                                                          |
| priority     | Category or type of workload (e.g., betbuilder prematch, inplay, lineups, etc.) |
| priority_int | Numeric workload weight representing the importance or intensity of each record |
| match_id     | Unique identifier for each workload entry (e.g., match or process instance)     |

**Dashboard Structure & Technical Explanation**

**Table 1C — Weighted Priority Score by Day**

**Purpose:**
Summarizes the **total weighted workload** score per day across the last 7 days.

**Technical Details:**

* Aggregates workload weights (`priority_int`) by date.
* Displays results as “Day –6” through “Day 0” to indicate relative time.
* Custom formatting removes totals and adjusts headers for alignment with the Python report.

**Workload Forecast (Weighted Priority Score)**

**Purpose:**
Visualizes the daily progression of total workload to forecast upcoming demand trends.

**Technical Details:**

* Line chart representing total weighted workload per calendar day.
* X-axis: date timeline
* Y-axis: weighted workload (summed values)
* Displays variation in daily workload levels and trend direction.


**Week-over-Week Workload by Hour (ISO Week: Mon–Sun)**

**Purpose:**
Compares **hourly workload profiles** across three consecutive ISO weeks.

**Technical Details:**

* Three overlaid lines represent: *Two Weeks Ago*, *Last Week*, and *This Week*.
* X-axis: 24-hour clock (0–23)
* Y-axis: total weighted workload by hour
* Enables comparison of workload behavior across weeks.

**Week-over-Week Hourly Profile by Weekday**

**Purpose:**
Analyzes **hourly workload variations per weekday** across the past three weeks.

**Technical Details:**

* Consists of seven subplots (Mon–Sun).
* Each subplot shows three weekly lines (Two Weeks Ago, Last Week, This Week).
* Each chart maintains uniform axis scales for visual consistency.

**Current Week Hourly Profile by Weekday**

**Purpose:**
Focuses solely on the **current week’s hourly patterns**, providing real-time workload insights.

**Technical Details:**

* Displays current week only.
* One line per weekday showing workload variation by hour.
* Consistent scaling across charts for fair comparison.

**Priority Mix by Day (Normalized Share 0–1)**

**Purpose:**
Depicts the **proportional distribution** of each workload priority over the past 7 days.

**Technical Details:**

* Each day’s total workload normalized to **1.0 (100%)**.
* Y-axis: fractional share (0.0–1.0).
* X-axis: daily dates.
* Colors: represent different priority categories.
* Power BI auto-manages Y-axis tick spacing (fixed 0.2 intervals are not natively supported).

**Analytical Value**

* Provides multi-dimensional insight into workload coverage.
* Enables trend, hourly, and compositional analysis from one unified dashboard.
* Supports week-over-week and day-level forecasting.
* Helps identify workload concentration, distribution shifts, and performance bottlenecks.


