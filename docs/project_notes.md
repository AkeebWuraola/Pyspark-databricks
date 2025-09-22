## Databricks

you can sign up for databricks free edition on the web: [Databricks][https://dbc-78bbccd4-217f.cloud.databricks.com/?autoLogin=true&o=835715601743406&dbx_source=www&riid=aa546fc0-0fec-49df-9f19-68bd5afcba08]

To handle metadata in databricks, you need to create a catalog
Catalog is the data management feature, this is equivalent to database in sql.
Databricks free version is connected to AWS datalake
Inside the catalog is where you create schemas, here you can follow the medallion architecture to create the various schemas. In addition, you have to also create the source schema that acts as a storage for your source data.
In the schemas, you create volumes to sotre your data

create a folder in your workspace that houses your notebooks for your spark projects

Notebooks are the building blocks of spark code.

To access your uploaded data files in the source schema, you have to first connect to your environment i.e severless compute (top right )
