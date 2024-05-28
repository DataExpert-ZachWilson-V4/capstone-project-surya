Capstone Project: Stock Market Data Analysis

Overview:

This project aims to analyze stock market data, focusing on Nvidia (NVDA), Tesla (TSLA), and other tech stocks. The analysis will be event-driven, with data streamed and processed every hour. AWS services will be utilized to build and deploy the project.

Architecture:

Data Source: Alpha Vantage API for fetching stock data.
AWS Services:
AWS Lambda: For fetching and processing data.
Amazon S3: For storing raw and processed data.
Amazon Kinesis: For streaming data.
AWS Glue: For data cataloging and ETL.
Amazon Athena: For querying data.
Amazon CloudWatch: For scheduling and monitoring.

Prerequisites:

1. AWS account with appropriate permissions.
2. Alpha Vantage API key.
3. Python 3.x installed locally.
4. AWS CLI configured on your local machine.
5. Boto3 (AWS SDK for Python) installed.

Data Model:

1. Fact Table: fact_stock_prices

This table contains the core transactional data, including stock prices and volumes.

Columns:

fact_id: Primary Key (auto-increment)
symbol: Stock symbol (e.g., NVDA, TSLA)
date: Date of the stock price (dimension reference)
time: Time of the stock price (dimension reference)
open_price: Opening price of the stock
high_price: Highest price of the stock during the period
low_price: Lowest price of the stock during the period
close_price: Closing price of the stock
adjusted_close: Adjusted closing price
volume: Number of shares traded
inserted_at: Timestamp when the record was inserted

2. Dimension Table: dim_symbol

This table contains details about the stock symbols.

Columns:

symbol_id: Primary Key
symbol: Stock symbol (e.g., NVDA, TSLA)
company_name: Full name of the company
sector: Sector of the company (e.g., Technology)
industry: Industry of the company (e.g., Semiconductors)
country: Country where the company is based

3. Dimension Table: dim_date

This table contains details about dates to facilitate time-based analysis.

Columns:

date_id: Primary Key
date: Date (e.g., 2023-01-01)
day: Day of the month (1-31)
month: Month of the year (1-12)
quarter: Quarter of the year (1-4)
year: Year (e.g., 2023)
day_of_week: Day of the week (1-7)
is_weekend: Indicator if the date is a weekend (Yes/No)

4. Dimension Table: dim_time

This table contains details about time to facilitate time-based analysis.

Columns:

time_id: Primary Key
time: Time (e.g., 14:00:00)
hour: Hour of the day (0-23)
minute: Minute of the hour (0-59)
second: Second of the minute (0-59)
