# Cloud-native Trino (prestosql) + Hive + Minio + Superset
## Technologies:
### Query Engine is `Trino (PrestoSQL)`
### Metadata Store is `Apache Hive`
### Object Storage is `Minio (S3 compatable)`
### Data Viz is `Apache Superset`

## Get things running
1. Clone repo
2. Install docker + docker-compose
3. Run `docker-compose --compatibility up`
4. Run `bash bootstrap-superset.sh`
4. Done! Checkout the service endpoints:

Trino: `http://localhost:8080/ui/` (username can be anything) <br>
Minio: `http://localhost:9001/` (username: `minio_access_key`, password: `minio_secret_key`)<br>
Superset: `http://localhost:8088/` (username: `admin`, password: `admin`)<br>

## Connect to Trino in Superset:
1. Go to `data` dropdown and click `databases`
2. Click the `+ database` button
3. For `Select a database to connect` choose `presto`
4. In `SQLALCHEMY URI` put `trino://hive@trino-coordinator:8080/hive`
5. Switch over to `Advanced` tab
5. In `SQL Lab` select all options
5. In `Security` select `Allow data upload`

## Use case : trino-taxi-data

- https://docs.stackable.tech/home/stable/demos/trino-taxi-data.html

- Dataset : https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page


trino-taxi-data


Install the required Stackable operators.

Spin up the following data products:

- Superset: A modern data exploration and visualization platform. This demo utilizes Superset to retrieve data from Trino via SQL queries and build dashboards on top of that data.

- Trino: A fast distributed SQL query engine for big data analytics that helps you explore your data universe. This demo uses it to enable SQL access to the data.

- MinIO: A S3 compatible object store. This demo uses it as persistent storage to store all the data used

- Hive metastore: A service that stores metadata related to Apache Hive and other services. This demo uses it as metadata storage for Trino.

- Open policy agent (OPA): An open-source, general-purpose policy engine unifying policy enforcement across the stack. This demo uses it as the authorizer for Trino, which decides which user can query

  which data.

Load test data into S3. It contains 2.5 years of New York City taxi trips.

Make data accessible via SQL in Trino.

Create Superset dashboards for visualization of the data.
  
 
