Capstone Project: Stock Market Data Analysis

Overview

This project aims to analyze stock market data, focusing on Nvidia (NVDA), Tesla (TSLA), and other tech stocks. The analysis will be event-driven, with data streamed and processed every hour. AWS services will be utilized to build and deploy the project.

Architecture
Data Source: Alpha Vantage API for fetching stock data.
AWS Services:
AWS Lambda: For fetching and processing data.
Amazon S3: For storing raw and processed data.
Amazon Kinesis: For streaming data.
AWS Glue: For data cataloging and ETL.
Amazon Athena: For querying data.
Amazon CloudWatch: For scheduling and monitoring.

Prerequisites
AWS account with appropriate permissions.
Alpha Vantage API key.
Python 3.x installed locally.
AWS CLI configured on your local machine.
Boto3 (AWS SDK for Python) installed.
