# Amazon Reviews Analysis with PySpark

![PySpark](https://img.shields.io/badge/PySpark-3.2.2-orange)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-12-blue)
![AWS](https://img.shields.io/badge/AWS-S3%20|%20RDS-yellow)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

## Project Overview

This project analyzes Amazon product reviews using big data technologies to determine if there's a bias toward favorable reviews from Amazon Vine program members. The analysis leverages Apache Spark for distributed processing and AWS for data storage and database hosting.

## Problem Statement
Amazon's Vine program allows manufacturers and publishers to receive reviews for their products by providing them to Amazon Vine members, who are then required to publish a review. This raises an important question:

**Are Vine reviews biased? Do Vine members give higher ratings than non-Vine reviewers?**

Understanding this potential bias is crucial for:
- Consumers relying on reviews for purchasing decisions
- Amazon's review credibility and marketplace integrity
- Vendors considering participation in the Vine program
- Data scientists studying review authenticity and influence

## Key Capabilities

- **ETL Pipeline**: Extract, transform, and load large datasets from S3 to PostgreSQL
- **Big Data Processing**: Handle millions of Amazon reviews efficiently with PySpark
- **Statistical Analysis**: Calculate and compare rating distributions between paid and unpaid reviews
- **Cloud Integration**: Seamless workflow between AWS S3 and RDS services

## Technologies Used

- **Apache Spark 3.2.2**: For distributed processing of large datasets
- **Python**: For data transformation and analysis logic
- **Jupyter Notebooks**: For interactive development and visualization
- **AWS S3**: Source data storage
- **AWS RDS (PostgreSQL)**: Processed data storage
- **JDBC**: For database connectivity

## Key Findings

The analysis of Amazon Wireless product reviews revealed:

| Review Type | Total Reviews | 5-Star Reviews | 5-Star Percentage |
|-------------|---------------|----------------|-------------------|
| Vine (Paid) | 613           | 222            | 36.22%            |
| Non-Vine    | 64,968        | 30,543         | 47.01%            |
| **Overall** | **65,581**    | **30,765**     | **46.91%**        |

**Insight**: Contrary to potential assumptions, Vine program (paid) reviewers gave proportionally fewer 5-star ratings than regular customers, suggesting no positive bias in the Vine program for the Wireless product category.

## Project Structure

```
amazon-reviews-analysis/
│
├── Amazon_Reviews_ETL.ipynb        # ETL pipeline for processing Amazon reviews
├── Vine_Review_Analysis.ipynb      # Statistical analysis of Vine vs. non-Vine reviews
└── README.md                       # Project documentation
```

## Implementation Details

## ETL Process

1. **Extract**: Load Amazon review data from S3 in TSV format
2. **Transform**: Create normalized tables for:
   - Customer data
   - Product information
   - Review metadata
   - Vine review details
3. **Load**: Store transformed data in PostgreSQL for analysis

## Analysis Methodology

1. Filter reviews with significant interaction (20+ votes)
2. Further filter to reviews with high-quality feedback (50%+ helpful votes)
3. Split the dataset between Vine (paid) and non-Vine reviewers
4. Calculate and compare rating distributions

## Running the Project

## Prerequisites

- Python 3.7+
- Apache Spark 3.x
- PostgreSQL JDBC driver
- AWS account with S3 and RDS access

## Setup Instructions

1. Clone the repository
2. Install dependencies: `pip install -r requirements.txt`
3. Configure database connection parameters
4. Run notebooks in sequence: ETL first, then Analysis

## Skills Demonstrated

- **Big Data Processing**: Efficient handling of large datasets using PySpark
- **Cloud Services Integration**: Working with AWS S3 and RDS
- **Data Engineering**: Building robust ETL pipelines
- **Data Analysis**: Statistical comparison and hypothesis testing
- **Data Visualization**: Clear presentation of analysis results
