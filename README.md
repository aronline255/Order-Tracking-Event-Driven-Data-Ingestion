# Order-Tracking-Event-Driven-Data-Ingestion

The Client is a Logistics company. The Client sends order details files daily to ADLS source. Load data from csv source files in ADLS Source folder to Delta table (staging table) where it is overwritten. The Source files are moved to an Archive folder. The data should be processed such that if 'NA' value in status column should be left blank or with no value.
The data from staging delta table is then sent to target delta table where the operation is upsert. The notebook is linked to github account. The source files in ADLS gen2 should be deleted at 11 pm daily. Also, create a databricks workflow to start the tasks whenever a new file is loaded into the source folder in ADLS.

