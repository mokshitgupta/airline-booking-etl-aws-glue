# ✈️ Airline Booking ETL with AWS Glue

This project demonstrates a simple ETL pipeline using **AWS Glue** to process airline booking data from S3.

## 📌 Objective

Extract booking data, transform it by filtering only **confirmed bookings**, and load the result into another S3 bucket.

## 🧰 Services Used

- **AWS Glue** (Jobs, Crawlers, Data Catalog)
- **Amazon S3** (Raw and Processed data)
- **AWS Glue Studio**
- **AWS Athena** (for query testing)

## 📁 Data Flow

1. 📥 **Input**: S3 bucket containing raw booking CSV files.
2. ⚙️ **Transformation**: Glue job filters only rows with `booking_status = CONFIRMED`.
3. 📤 **Output**: Cleaned data written back to a new S3 bucket.

## 📝 Glue Script

See [`glue_etl_confirmed_bookings.py`](glue_etl_confirmed_bookings.py)

## 📸 Screenshots

All setup screenshots are in the [screenshots](screenshots/) folder.

## 📊 Sample Query (Athena)

```sql
SELECT * FROM airline_booking_db.bookings_confirmed
WHERE booking_status = 'CONFIRMED';
