Uber Operations Analytics Dashboard

A Power BI dashboard I built to dig into Uber-style ride booking data — how demand moves over time, where the revenue comes from, why rides get cancelled, and how customers and drivers rate each other.

Why I built this

I wanted to work with a dataset that actually resembled real ride-hailing operations data instead of a toy dataset, and practice going through the full workflow — cleaning messy data, modeling it, writing DAX, and then designing a report someone could actually use to make decisions, not just look at.

The data

Working table has 50,000+ booking records with fields like Booking_ID, Booking_Status, Booking_Value, Customer_ID, Vehicle_Type, Payment_Method, Ride_Distance, Date, Customer_Rating, Driver_Ratings, and the cancellation fields (Canceled_Rides_by_Customer, Canceled_Rides_by_Driver). Did the cleaning and shaping in Power Query before touching the model.

Tools
Power BI Desktop (modeling + report build)
Power Query for cleanup
DAX for the measures
What's in the report

I split it into 5 pages instead of cramming everything onto one:

Overall – total bookings, total booking value, a ride volume trend line, and a breakdown of booking status
Vehicle Type – same KPIs but sliced by vehicle category, so you can see which types are pulling their weight
Revenue – revenue by payment method plus a top 5 customers table
Cancellation – cancellation rate, successful vs cancelled bookings, and a split of who's cancelling more — customers or drivers
Ratings – customer and driver rating KPIs side by side

All pages share the same Date slicer, and I added nav buttons so you're not stuck scrolling through page tabs.

Measures I wrote

A few of the main ones:

Count of Booking_ID – total bookings
Sum of Booking_Value – total revenue
CanceledBookingsCount – total cancellations
Count of Canceled_Rides_by_Customer / Count of Canceled_Rides_by_Driver – who's cancelling
Average of Customer_Rating / Average of Driver_Ratings
Sum of Ride_Distance / Average of Ride_Distance
What I found
Ride volume isn't flat — there are clear peak periods in the trend line.
Cancellations aren't evenly split — breaking it down by customer vs driver actually mattered here, they don't cancel at the same rate.
A small set of customers account for a disproportionate chunk of revenue (see the Top 5 Customers table).
Payment method has a real effect on revenue mix, not just transaction count.
Repo contents
├── UBER_DASHBOARD.pbix
└── README.md
Running it

Just open UBER_DASHBOARD.pbix in Power BI Desktop — no setup needed. Use the Date slicer or the nav buttons to move between pages.

About me

Surya Bhola — data analyst working mainly in SQL, Python, Excel, and Power BI. [UBER DASHBOARD (1).pdf](https://github.com/user-attachments/files/32227689/UBER.DASHBOARD.1.pdf)
