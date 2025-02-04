# 🚖 OLA Data Analytics Project

## 📌 Project Objective
This project aims to analyze and optimize ride bookings and cancellations in the OLA system using SQL and Power BI.

### Key Goals:
- ✅ Ensure customer cancellations remain below **7%**
- ✅ Ensure driver cancellations remain below **18%**
- 📈 Increase the number of orders on **weekends and match days**
- 🛑 Keep incomplete rides under **6%**
- 🍕 Maintain high order value on weekends in the **Food Category**
- 🇮🇳 Keep around **67%** of orders from India
- 🔢 Ensure **10-digit Order IDs** starting with `CNR`
- 💰 Keep **70%** of orders under ₹500, **28%** between ₹500-₹1000, and the rest above ₹1000

---

## 📊 Dataset Used
This dataset includes ride booking details with the following key attributes:

| Column Name | Description |
|------------|-------------|
| Date | Booking date |
| Time | Booking time |
| Booking_ID | Unique booking identifier |
| Booking_Status | Status of the ride (Success, Cancelled, Incomplete) |
| Customer_ID | Unique customer identifier |
| Vehicle_Type | Type of vehicle booked |
| Pickup_Location | Starting point of the ride |
| Drop_Location | Destination point |
| V_TAT | Vehicle Turnaround Time |
| C_TAT | Customer Turnaround Time |
| cancelled_Rides_by_Customer | Cancellations by customers |
| cancelled_Rides_by_Driver | Cancellations by drivers |
| Incomplete_Rides | Whether the ride was incomplete |
| Incomplete_Rides_Reason | Reason for incomplete rides |
| Booking_Value | Total fare for the booking |
| Payment_Method | Payment method used (UPI, Card, Cash) |
| Ride_Distance | Distance covered in the ride |
| Driver_Ratings | Rating given to the driver |
| Customer_Rating | Rating given by the customer |

---

## 🔍 SQL Queries
Here are some important SQL queries used in the analysis:

1️⃣ Retrieve all successful bookings:
```sql
SELECT * FROM bookings WHERE Booking_Status = 'Success';
```

2️⃣ Find the average ride distance for each vehicle type:
```sql
SELECT Vehicle_Type, AVG(Ride_Distance) as avg_distance FROM bookings GROUP BY Vehicle_Type;
```

3️⃣ Get the total number of rides cancelled by customers:
```sql
SELECT COUNT(*) FROM bookings WHERE Booking_Status = 'cancelled by Customer';
```

4️⃣ List the top 5 customers who booked the highest number of rides:
```sql
SELECT Customer_ID, COUNT(Booking_ID) as total_rides 
FROM bookings 
GROUP BY Customer_ID 
ORDER BY total_rides DESC 
LIMIT 5;
```

5️⃣ Get the number of rides cancelled by drivers due to personal and car-related issues:
```sql
SELECT COUNT(*) FROM bookings WHERE cancelled_Rides_by_Driver = 'Personal & Car related issue';
```

6️⃣ Find the maximum and minimum driver ratings for Prime Sedan bookings:
```sql
SELECT MAX(Driver_Ratings) as max_rating, MIN(Driver_Ratings) as min_rating FROM bookings WHERE Vehicle_Type = 'Prime Sedan';
```

7️⃣ Retrieve all rides where payment was made using UPI:
```sql
SELECT * FROM bookings WHERE Payment_Method = 'UPI';
```

8️⃣ Find the average customer rating per vehicle type:
```sql
SELECT Vehicle_Type, AVG(Customer_Rating) as avg_customer_rating FROM bookings GROUP BY Vehicle_Type;
```

9️⃣ Calculate the total booking value of rides completed successfully:
```sql
SELECT SUM(Booking_Value) as total_successful_value FROM bookings WHERE Booking_Status = 'Success';
```

🔟 List all incomplete rides along with the reason:
```sql
SELECT Booking_ID, Incomplete_Rides_Reason FROM bookings WHERE Incomplete_Rides = 'Yes';
```

---

## 📊 Power BI Insights
Here are the key visualizations created in Power BI:

📌 **Ride Volume Over Time** – Analyzing trends in booking volume
📌 **Booking Status Breakdown** – Success vs. Cancelled vs. Incomplete rides
📌 **Top 5 Vehicle Types by Ride Distance** – Finding popular vehicle types
📌 **Average Customer Ratings by Vehicle Type** – Understanding service satisfaction
📌 **Cancelled Rides Reasons** – Breakdown of cancellation causes
📌 **Revenue by Payment Method** – Analyzing earnings based on payment types
📌 **Top 5 Customers by Total Booking Value** – Identifying high-value customers
📌 **Ride Distance Distribution Per Day** – Understanding ride patterns
📌 **Driver Ratings Distribution** – Evaluating driver performance
📌 **Customer vs. Driver Ratings** – Comparing both perspectives

---

## 🖥️ Dashboard Interaction

📌 **View the Dashboard:** [🔗 Click Here](https://github.com/manavpatel7220/olaDataAnalyticsproject/blob/main/ola.pdf)

📌 **View the Dataset:** [🔗 Click Here](https://github.com/manavpatel7220/olaDataAnalyticsproject/blob/main/ola.pbix)

---

## 🚀 How to Use
1️⃣ **Clone the Repository**
```bash
git clone https://github.com/your-username/OLA-DataAnalytics-Project.git
```
2️⃣ **Import the Dataset** into SQL & Power BI
3️⃣ **Run SQL Queries** for insights
4️⃣ **Use Power BI Dashboards** to visualize data trends

---

## 📢 Contributions & Feedback
💡 Suggestions and contributions are welcome! Feel free to **fork**, create a **pull request**, or open an **issue**.

---

### ⭐ Don't forget to star this repo if you found it useful!
