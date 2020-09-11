# LAB: Google Cloud Fundamentals: Getting Started with BigQuery
---
## Objectives:
---


*In this lab, you learn how to perform the following tasks:*

- Load data from Cloud Storage into BigQuery.

- Perform a query on the data in BigQuery.

---
## STEPS TO LOAD DATA FROM CLOUD STORAGE INTO BIGQUERY
---


1. In the GCP Console, on the Navigation menu (Navigation menu), click BigQuery & then click Done.


2. Create a new dataset within your project by selecting your project in the Resources section, then clicking on _**CREATE DATASET**_ on the right.


3. In the _**Create Dataset**_ dialog, for **Dataset ID**, type **logdata**.


4. For _**Data location**_, select the continent closest to the region your project was created in. click **Create dataset**.


5. Create a new table in the **logdata** to store the data from the CSV file.


6. Click on **_Create Table_**. On the _**Create Table**_ page, in the **Source** section:

	- For **Create table from**, choose select **Google Cloud Storage**, and in the field, type `gs://cloud-training/gcpfci/access_log.csv`.

	- Verify **File format** is set to _CSV_.


*  When you have created a table previously, the Create from Previous Job option allows you to quickly use your settings to create similar tables.


7. In the **Destination** section:

	- For **Dataset name**, leave **logdata** selected.

	- For **Table name**, type **accesslog**.

	- For **Table type**, **Native table** should be selected.


8. Under **Schema** section, for **Auto detect** check the **Schema and input Parameters**.
Accept the remaining default values and click **Create Table**.

* BigQuery creates a load job to create the table and upload data into the table (this may take a few seconds).


9. When the load job is complete, click **logdata > accesslog**.


10. On the table details page, click **Details** to view the table properties, and then click **Preview** to view the table data.

* Each row in this table logs a hit on a web server. The first field, string_field_0, is the IP address of the client. The fourth through ninth fields log the day, month, year, hour, minute, and second at which the hit occurred. In this activity, you will learn about the daily pattern of load on this web server.


# Click _Check my progress_ to verify the objective.


---
## STEPS FOR PERFORMING A QUERY ON THE DATA USING THE BIGQUERY WEB UI
---

1. In the Query editor window, type (or copy-and-paste) the following query:

	 `select int64_field_6 as hour, count(*) as hitcount from logdata.accesslog
group by hour
order by hour`.

* Notice that the Query Validator tells you that the query syntax is valid (indicated by the green check mark) and indicates how much data the query will process.


2. Click **Run** and examine the results.



---
## STEPS FOR PERFORMING A QUERY ON THE DATA USING BQ COMMAND
---
1. On the **Google Cloud Platform** Console, click **Activate Cloud Shell** 
then click Continue.

2. At the Cloud Shell prompt, enter this command:

	`bq query "select string_field_10 as request, count(*) as requestcount from logdata.accesslog group by request order by requestcount desc"`

* The first time you use the bq command, it caches your Google Cloud Platform credentials, and then asks you to choose your default project. Choose the project that Qwiklabs assigned you to. Its name will look like qwiklabs-gcp- followed by a hexadecimal number.

* The bq command then performs the action requested on its command line. What URL offered by this web server was most popular? Which was least popular?
		 

##  Congratulations!
*  In this lab, you loaded data stored in Cloud Storage into a table hosted by Google BigQuery. You then queried the data to discover patterns.