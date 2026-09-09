TRAVEL DATA ENGINEERING PRACTICE PROJECT

Use this dataset to replicate an Azure end-to-end Data Engineering project.

Suggested architecture:
Source CSVs
  -> ADF
  -> ADLS Gen2 Bronze
  -> Databricks / PySpark
  -> Silver
  -> Gold
  -> Synapse Serverless SQL
  -> Power BI

Files:
customers.csv      Customer dimension
destinations.csv   Destination dimension
hotels.csv         Hotel dimension
transport.csv      Transport provider dimension
bookings.csv       Main fact/transaction dataset
reviews.csv        Reviews linked to bookings

Suggested Gold model:
fact_bookings
dim_customer
dim_destination
dim_hotel
dim_transport
dim_date
fact_reviews

Suggested practice:
1. Upload raw CSVs to ADLS Bronze.
2. Create an ADF pipeline to ingest/copy them.
3. Read Bronze data with Databricks.
4. Clean nulls, data types, duplicates and invalid records.
5. Create Silver tables.
6. Build Gold star schema.
7. Write Gold data as Parquet/Delta.
8. Query the Gold layer through Synapse Serverless SQL.
9. Create views for reporting.
10. Connect Power BI to the serving layer.

Business questions:
- Revenue by destination and month
- Top 10 destinations by booking revenue
- Cancellation rate by booking channel
- Average booking value by customer type
- Hotel revenue by star rating
- Average trip duration by destination
- Customer repeat-booking rate
- Rating vs revenue
- Revenue by country/region
- Mobile App vs Website performance

Recommended interview challenge:
Build the entire pipeline without copying the project. Document why ADF, ADLS, Databricks, Synapse and Power BI are each used.
