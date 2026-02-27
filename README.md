## **Project Description – Customer 360 ETL Pipeline**

This project uses the Faker API to generate fake sales, customer, and product data, and stores these datasets as CSV files in the source layer.
The pipeline follows a medallion architecture:
- Bronze Layer: Ingests data incrementally from the CSV files into Delta tables, capturing raw data.
- Silver Layer: Cleans and transforms the bronze data into usable datasets while removing duplicates and errors.
- Gold Layer: Implements SCD Type 2 for dimension tables on top of Delta tables and prepares report-ready datasets for analytics.

The ETL process is orchestrated using Databricks Workflows, which manage the DAG execution, trigger tasks, and send alerts on completion or failure. The job configuration and orchestration details are stored in a YAML file, making it easy to create and manage the pipeline.
This setup ensures incremental processing, data quality, and report-ready outputs while leveraging the scalability and efficiency of Databricks.


## **Databricks Customer 360 ETL Pipeline Setup Guide**

This project contains the ETL pipeline for the Customer 360 data processing in Databricks. The repository includes notebooks, job definitions, and environment requirements for building and running the pipeline.


#### **Project Setup Guide**

- Navigate to Workspace → Users → Your Email ID in Databricks.

- Create a new Git folder by clicking the top-right menu → Create → Git Repository.

- Enter the following details:

- Git Repo URL: https://github.com/shandro-dev/databricks_customer_360_etl_pipeline.git

- Git Folder Name: databricks_customer_360_etl_pipeline

- Git Provider: GitHub

- Click Create.

- Move the Folder to Workspace 

- Click on the folder databricks_customer_360_etl_pipeline in your workspace.

- Inside the folder, you will see the project structure:

- customer_360_pipeline/

- notebooks/ – contains all notebooks

- jobs/ – contains job YAML filesfor jobs

- requirements.txt – Python dependencies

- From the top of the folder view:

- Click the branch name to create a new branch for your development.

- From the same menu, you can pull or push code to your branch.

- Create the Job for the ETL Pipeline

- Navigate to the jobs/ folder.

- Use the provided YAML file to create a job in Databricks.

- This will generate the ETL pipeline DAG workflow.

- The job will execute the ETL tasks as defined in the YAML file, including loading data, processing, and optimizing tables.

- Change the email from yaml file to your mail id asociated with databricks account.

- uncomment below 3 lines from notebook "data to source" for the initial run.
  -  NUM_CUSTOMERS = 3 
  -  NUM_PRODUCTS = 2   
  -  NUM_SALES = 10

#### **Folder Structure**

databricks_customer_360_etl_pipeline/
│
├── customer_360_pipeline/
│   ├── notebooks/
│   ├── jobs/
│   └── requirements.txt


#### **Notes**

- Ensure that all notebooks and dependencies are present in the folder before running the job.
- Use a separate branch for development to avoid conflicts with the main branch.
- If using Git integration, always pull the latest changes before starting development.



#### **Author**

Project maintained by: Shandro Mitra

Email: shandromitra@gmail.com