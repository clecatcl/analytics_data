\# analytics\_data



DBT project for the Local Bike Shop dataset.  

Transforms raw data into staging, intermediate, and mart tables for analytics and dashboarding in BigQuery.



\## Project Structure



\- \*\*models/\*\* – SQL transformations, organized by `stg\_`, `int\_`, and `mrt\_` models

\- \*\*macros/\*\* – reusable DBT macros

\- \*\*seeds/\*\* – CSV data to load

\- \*\*snapshots/\*\* – historical tracking of tables

\- \*\*analyses/\*\* – exploratory queries and reporting

\- \*\*tests/\*\* – DBT tests



\## Configuration



1\. Install Python and dbt.

2\. Create a BigQuery service account JSON file.

3\. Create `profiles.yml` at `C:\\Users\\<User>\\.dbt\\profiles.yml` with:



```yaml

analytics\_data:

&#x20; target: dev

&#x20; outputs:

&#x20;   dev:

&#x20;     type: bigquery

&#x20;     method: service-account

&#x20;     project: <YOUR\_GCP\_PROJECT>

&#x20;     dataset: local\_bike

&#x20;     threads: 1

&#x20;     keyfile: C:\\path\\to\\service-account.json

&#x20;     location: US



