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
[SPARK]
spark_version = spark-3.2.2
driver_path = /content/postgresql-42.2.16.jar

[AWS]
# Replace with your S3 bucket information
s3_reviews_url = https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Wireless_v1_00.tsv.gz

[DATABASE]
# Replace these with your actual database credentials
jdbc_url = jdbc:postgresql://your-database-url:5432/database-name
user = your-username
password = your-password
driver = org.postgresql.Driver

[ETL]
# Mode can be "append", "overwrite", "ignore", or "error"
write_mode = append
