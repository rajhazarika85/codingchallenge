# Coding Challenge

This code challenge demonstrates ETL of data using Python in Jupyter Notebook to Google BigQuery.

## Description
The objective of the code challenge is to perform Extraction Transformation and Load ([ETL](https://en.wikipedia.org/wiki/Extract,_transform,_load)) on dataset from source: [https://archive.ics.uci.edu/ml/datasets/Online+Retail](https://archive.ics.uci.edu/ml/datasets/Online+Retail). Python is used for ETL and dataset is uploaded to [Google BigQuery](https://cloud.google.com/bigquery/?utm_source=google&utm_medium=cpc&utm_campaign=japac-IN-all-en-dr-bkwsrmkt-all-all-trial-e-dr-1009882&utm_content=text-ad-none-none-DEV_c-CRE_442449534209-ADGP_Hybrid%20%7C%20BKWS%20-%20EXA%20%7C%20Txt%20~%20Data%20Analytics%20~%20BigQuery_bigquery-KWID_43700054974618275-aud-970366092687%3Akwd-47616965283&userloc_1006644-network_g&utm_term=KW_bigquery&gclid=CjwKCAjw8cCGBhB6EiwAgOReyxv1rKCi5aYzpZg84omfQ_My9ApKFO2L_u9h2Am6fuoM0AObg_nuWRoC3-sQAvD_BwE&gclsrc=aw.ds) and then visualization is performed using [Google Data Studio](https://datastudio.google.com/overview)

## Dependencies
Following python packages have been used for the solution. Please use the package manager [pip](https://pip.pypa.io/en/stable/) to install the below-listed dependencies.

```bash
pip install pandas 
pip install scikit-learn
pip install matplotlib
pip install pandas-gbq
pip install google-auth

```
## Quick Start
- git clone https://github.com/rajhazarika85/codingchallenge.git
- Open 'Emil Group Coding Challenge.ipynb' in Jupyter Notebook and run all cells in sequence
- (Create Google BigQuery dataset)[https://cloud.google.com/bigquery/docs/datasets]
- (Create a service account in GCP)[https://cloud.google.com/iam/docs/creating-managing-service-accounts] with access to the Google BigQuery dataset or ask for permission to the dataset. Download the key into JSON file and save it in the root folder. The code example to use the JSON file with key is shown below



```bash
   #Service account credentials
   credentials = service_account.Credentials.from_service_account_file('projectid-credentials.json')
```

- Access the dashboards in Google Data Studio or ask for permission to the dashboard. **[Click here to view the dashboard](https://datastudio.google.com/reporting/e91a02ba-a3f1-4c25-b7b0-5654b95ac7fd)** 




## Dataset
Dataset can be download [here](https://archive.ics.uci.edu/ml/datasets/Online+Retail).
The dataset contains sales transaction occurred between 01/12/2010 and 09/12/2011 of a UK based online retail. The company mainly sells unique all-occasion gifts. Many customers of the company are wholesalers.

- **InvoiceNo**: Invoice number. Nominal, a 6-digit integral number uniquely assigned to each transaction. If this code starts with letter 'c', it indicates a cancellation.
- **StockCode**: Product (item) code. Nominal, a 5-digit integral number uniquely assigned to each distinct product.
- **Description**: Product (item) name. Nominal.
- **Quantity**: The quantities of each product (item) per transaction. Numeric.
- **InvoiceDate**: Invoice Date and time. Numeric, the day and time when each transaction was generated.
- **UnitPrice**: Unit price. Numeric, Product price per unit in sterling.
- **CustomerID**: Customer number. Nominal, a 5-digit integral number uniquely assigned to each customer.
- **Country**: Country name. Nominal, the name of the country where each customer resides.


| #| |
| ----------- | ----------- |
| Rows| 541909|
| Columns| 8|

## Data preprocessing and Solution 
Following data preprocessing has been done
- Checking datatypes
- Checking null values
- Converting 'StockCode' to upper case
- Extracting product category from 'Description' column
- Calculating Order status
- Clustering using k-means from scikit-learn
- Created service account in GCP with permission to access Google BigQuery dataset
- Connect to Google Cloud API and upload dataframe

## Google Cloud 
- **Google BigQuery** is used as data warehouse
- **Google Data Studio** is used for visualization and dashboard




## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

