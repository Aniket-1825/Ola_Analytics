# 🚖 Ola Analytics — End-to-End Ride Data Analysis

![SQL](https://img.shields.io/badge/SQL-MySQL-blue?style=flat-square&logo=mysql&logoColor=white)
![PowerBI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow?style=flat-square&logo=powerbi&logoColor=black)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square)

An end-to-end data analysis project on Ola ride bookings, using **MySQL** for data extraction and **Power BI** for interactive dashboards. The project uncovers patterns in ride trends, cancellations, revenue, and user behavior to support business decision-making.

---

## 📌 Problem Statement

Ride-hailing platforms like Ola generate massive volumes of booking data daily. Without proper analysis, valuable signals — such as why rides are getting cancelled, which vehicle types are most profitable, or how customer ratings vary — remain hidden. This project explores those questions systematically using SQL and Power BI.

---

## 🎯 Objectives

- Identify overall ride volume trends and booking success rates
- Understand cancellation patterns — by customers and drivers
- Analyse revenue performance across different vehicle types and payment methods
- Study driver and customer ratings to spot service quality issues
- Surface incomplete ride reasons to reduce operational losses

---

## 🗂️ Project Structure

```
Ola_Analytics/
│
├── ola_Query.sql          # All SQL Views for data extraction & analysis
├── Ola-Analysis.pbix      # Power BI dashboard file
└── README.md
```

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **MySQL** | Data extraction, filtering, aggregation via SQL Views |
| **Power BI** | Interactive dashboards and visual storytelling |
| **GitHub** | Version control and project sharing |

---

## 🔍 SQL Analysis — Key Queries

The analysis is structured into **10 SQL Views**, each answering a specific business question:

| # | View Name | Business Question |
|---|---|---|
| 1 | `Successful_Bookings` | Which rides completed successfully? |
| 2 | `ride_distance_for_each_vehicle` | What is the average ride distance per vehicle type? |
| 3 | `cancelled_rides_by_customers` | How many rides did customers cancel? |
| 4 | `Top_5_Customers` | Who are the top 5 highest-booking customers? |
| 5 | `Rides_cancelled_by_Drivers_P_C_Issues` | How many driver cancellations were due to personal/car issues? |
| 6 | `Max_Min_Driver_Rating` | What is the rating range for Prime Sedan drivers? |
| 7 | `UPI_Payment` | Which rides were paid via UPI? |
| 8 | `AVG_Cust_Rating` | What is the average customer rating per vehicle type? |
| 9 | `total_successful_ride_value` | What is the total revenue from successful rides? |
| 10 | `Incomplete_Rides_Reason` | What reasons are causing incomplete rides? |

### Sample Query

```sql
-- Top 5 customers by number of bookings
CREATE VIEW Top_5_Customers AS
SELECT Customer_ID, COUNT(Booking_ID) AS total_rides
FROM bookings
GROUP BY Customer_ID
ORDER BY total_rides DESC
LIMIT 5;
```

---

## 📊 Power BI Dashboard

The `.pbix` file contains an interactive dashboard with the following views:

- **Ride Volume Overview** — Total bookings, success rate, cancellation rate
- **Cancellation Analysis** — Breakdown by customer vs. driver, with reasons
- **Revenue Insights** — Booking value by vehicle type and payment method
- **Vehicle Type Performance** — Distance, ratings, and ride count per type
- **Customer & Driver Ratings** — Average ratings across segments

> 📂 Download [`Ola-Analysis.pbix`](./Ola-Analysis.pbix) and open in Power BI Desktop to explore.

---

## 💡 Key Insights

- **Cancellations** are a significant operational issue — driver-side cancellations due to personal/car issues represent a measurable loss in bookings
- **Prime Sedan** shows the widest range of driver ratings, indicating inconsistent service quality in the premium segment
- **UPI** is a dominant payment method, suggesting the customer base skews toward digital-first users
- **Top 5 customers** account for a disproportionate number of bookings — a loyalty programme targeting these users could boost retention
- **Incomplete rides** cluster around specific reasons that can be addressed through driver training or policy changes

---

## 🚀 How to Use This Project

**SQL Queries:**
1. Import your bookings dataset into MySQL
2. Run `ola_Query.sql` to create all 10 analysis views
3. Query any view directly: `SELECT * FROM Successful_Bookings;`

**Power BI Dashboard:**
1. Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free)
2. Open `Ola-Analysis.pbix`
3. Refresh the data source connection if needed

---

## 📸 Dashboard Preview

> _Add screenshots of your Power BI dashboard here_
> _(In your repo: click Add file → Upload files → drag your screenshot images)_

---

## 👤 Author

**Aniket Rathod**
Data Analyst | SQL · Python · Power BI
📍 Ahmedabad, India

[![LinkedIn]([www.linkedin.com/in/aniket-rathod-66b907372])
[![GitHub](https://img.shields.io/badge/GitHub-Profile-black?style=flat-square&logo=github)](https://github.com/Aniket-1825)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
