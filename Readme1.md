# Amazon Reviews Analysis

## Project Overview
This project analyzes Amazon product reviews using big data technologies to determine if there's a bias toward favorable reviews from paid Amazon Vine program members. The analysis uses PySpark to perform ETL (Extract, Transform, Load) operations and statistical analysis on large datasets.

![Amazon Reviews Analysis](https://img.shields.io/badge/Data%20Analysis-Big%20Data-blue)
![PySpark](https://img.shields.io/badge/Technology-PySpark-orange)
![AWS](https://img.shields.io/badge/Cloud-AWS-yellow)
![PostgreSQL](https://img.shields.io/badge/Database-PostgreSQL-blue)

## Problem Statement
Amazon's Vine program allows manufacturers and publishers to receive reviews for their products by providing them to Amazon Vine members, who are then required to publish a review. This raises an important question:

**Are Vine reviews biased? Do Vine members give higher ratings than non-Vine reviewers?**

Understanding this potential bias is crucial for:
- Consumers relying on reviews for purchasing decisions
- Amazon's review credibility and marketplace integrity
- Vendors considering participation in the Vine program
- Data scientists studying review authenticity and influence

## Project Structure
This repository contains two main components:

### 1. ETL Pipeline (Amazon_Reviews_ETL.ipynb)
- **Extract**: Retrieves Amazon review data from an AWS S3 bucket
- **Transform**: Processes and structures the data into appropriate dataframes
- **Load**: Transfers the processed data into a PostgreSQL database

### 2. Analysis (Vine_Review_Analysis.ipynb)
- Applies statistical methods to compare review patterns
- Filters reviews based on vote count and helpfulness 
- Compares 5-star rating percentages between Vine and non-Vine reviews
- Determines if there's a statistical bias in review ratings

## Key Findings
The analysis reveals that:
- **36.22%** of Vine (paid) reviews were 5-star
- **47.01%** of non-Vine (unpaid) reviews were 5-star

Contrary to what might be expected, Vine reviewers appear to be more critical in their ratings than non-Vine reviewers. This suggests that the Vine program might actually be encouraging more balanced and potentially more trustworthy reviews.

## Technologies Used
- **PySpark**: For big data processing
- **AWS S3**: Data source
- **PostgreSQL**: For data storage and retrieval
- **Python**: Core programming language
- **Jupyter Notebooks**: Development environment

## Getting Started

### Prerequisites
- Apache Spark (3.2.2+)
- Python 3.6+
- AWS account (to access S3 data)
- PostgreSQL database
- JDBC PostgreSQL driver

### Installation & Setup
1. Clone this repository
```
git clone https://github.com/yourusername/amazon-reviews-analysis.git
```

2. Install required dependencies
```
pip install findspark pyspark
```

3. Configure your PostgreSQL connection in the notebooks
```python
jdbc_url = "jdbc:postgresql://your-database-url:5432/database-name"
config = {
    "user": "your-username",
    "password": "your-password",
    "driver": "org.postgresql.Driver"
}
```

## Benefits & Applications
This project demonstrates:
- **Efficiency**: Processes millions of reviews quickly using distributed computing
- **Cost Reduction**: Helps vendors evaluate the ROI of paid review programs
- **Data-Driven Decision Making**: Provides quantitative analysis for marketplace strategy
- **Big Data Skills**: Showcases ability to handle large-scale data processing workflows
