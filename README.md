# Uber Ride Analytics Dashboard (Power BI)

An interactive Power BI dashboard that digs into one month of Uber ride data (July 2024). I built it to answer a few simple questions: how many rides actually get completed, why do the rest fall through, which vehicle types and payment methods bring in the most money, and how happy are drivers and customers?

The dashboard has five pages, and each one covers a different side of the business.

---

## What's in this repo

```
uber-dashboard/
├── UBER_DASHBOARD.pbix     # the Power BI file (open with Power BI Desktop)
├── images/                 # screenshots used in this README
└── README.md
```

To open the dashboard, download `UBER_DASHBOARD.pbix` and open it in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (it's free, Windows only).

---

## Dashboard pages

### 1. Overall

The landing page. It gives a quick health check of the whole month: total bookings, total booking value, how bookings break down by status, and how ride volume moves day to day.

![Overall page](images/overall.png)

- **20,407** total bookings with a combined booking value of about **₹1.11 crore (11,148,671)**
- About **62%** of bookings were completed successfully
- The rest were split between cancelled by driver (~18%), driver not found (~10%) and cancelled by customer (~10%)
- Daily volume stays in a fairly tight band of roughly 640 to 720 bookings, with a noticeable dip around the 27th

### 2. Vehicle Type

A side-by-side look at all seven vehicle categories: Prime Sedan, Prime SUV, Prime Plus, Mini, Auto, Bike and E-Bike.

![Vehicle type page](images/vehicle-type.png)

- Total booking value is almost identical across categories, so no single vehicle type dominates
- Success booking value ranges from about 935K (Prime Plus) to about 1M (Prime Sedan)
- Auto is the odd one out: average trip is only **10 km**, while every other type sits around **24 to 25.7 km**. That's why its total distance (18K) is far lower than the rest (41K to 48K)

### 3. Revenue

Where the money comes from, by payment method and by day.

![Revenue page](images/revenue.png)

- **Cash** is the biggest payment method (close to 4M), followed by **UPI** (about 2.8M)
- Credit and debit cards together make up a very small share
- Daily revenue is steady at around 9K to 10K, with a few higher days near the 22nd and 30th
- A Top 5 customers table shows the highest-spending customer IDs

### 4. Cancellation

This page digs into the problem on the overall page: why so many rides don't finish.

![Cancellation page](images/cancellation.png)

- **5,735** cancelled bookings out of 20,407, giving a **cancellation rate of 28.10%**
- **12,652** bookings were completed successfully
- Top reasons customers cancel: driver not moving towards pickup (29.3%), driver asked to cancel (26.5%), change of plans (19.6%), AC not working (15.4%) and wrong address (9.2%)
- Top reasons drivers cancel: personal and car related issues (34.6%), customer related issues (29.1%), customer coughing or unwell (20.3%) and more than the permitted number of people (16.0%)

### 5. Ratings

Average driver and customer ratings for each vehicle type.

![Ratings page](images/ratings.png)

- Both driver and customer ratings are very consistent, sitting right around **4.0** out of 5
- The spread across vehicle types is tiny (3.98 to 4.02), so ratings don't really separate the categories

---

## Key takeaways

1. **Cancellations are the biggest issue.** Almost 3 in 10 bookings never turn into a completed ride, and many of the reasons (driver not moving, driver asking to cancel, AC not working) are things the platform could actually improve.
2. **Cash still leads.** Even with UPI being popular, cash brings in the most revenue, and cards barely register.
3. **Autos are short-hop vehicles.** Their trip distance is less than half that of every other type.
4. **Service quality looks stable.** Ratings are almost flat across vehicle types, which suggests a consistent experience.

---

## Features

- Date range slicer on every page, so you can zoom into any window of the month
- Page navigation sidebar with custom icons
- Vehicle type icons in the tables for easier reading
- KPI cards, pie charts, column charts, line chart and tables

## Tools used

- **Power BI Desktop** for data modelling, DAX measures and visuals
- Custom icons and layout for the navigation and vehicle tables

---

## How to use it

1. Clone or download this repository
   ```bash
   git clone https://github.com/<your-username>/<your-repo-name>.git
   ```
2. Open `UBER_DASHBOARD.pbix` in Power BI Desktop
3. Use the date slicer and the left sidebar to move around

---

## Things I'd improve next

- The lower chart on the Revenue page is titled "Revenue By Payment Method" but actually shows revenue by day, so the title and axis label need fixing
- Add a filter for vehicle type and payment method across all pages
- Look at cancellations by time of day and pickup location to find where the problem is worst

---

## About me

Made by **<Your Name>** as part of my data analyst portfolio.

- LinkedIn: <your-linkedin-link>
- Email: <your-email>

If you have feedback or suggestions, feel free to open an issue or reach out.
