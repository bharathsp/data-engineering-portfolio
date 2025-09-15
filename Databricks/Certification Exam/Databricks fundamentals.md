# Databricks fundamentals

## Topics Covered:
1. Databricks SQL 
2. Databricks lakehouse platform
3. Data Intelligence
4. Databricks Architecture
5. Databricks Sceurity and Governance
6. Databricks Product and Features
7. Databricks data engineer and data science workspace 
8. Databricks machine learning

---

## Notes
1. Databricks acquired MosaicML in 2023 for creating and customizing generative AI models. It helps with training, customizing, and deploying generative AI applications.
2. Data Intelligence Platform = Data Lakehouse (An open unified solution for all your data) + Generative AI (Easily scale and use data and AI)

<img width="400" height="400" alt="image" src="https://github.com/user-attachments/assets/d75994f4-dc8b-4e0d-b602-b77942d92745" />
 Databricks product pillars:
 a. Lakeflow
   i. Connect - Provides services to connect to business datasources. Provide no code connectors makeing it easy to get data into databricks.
   <img width="1838" height="910" alt="image" src="https://github.com/user-attachments/assets/8e8e9a26-dcb4-4796-8194-8b6e01f46fd6" />

   ii. Delta Live Tables - Helps in creating reliable data pipelines. DLT automatically manages infrastructure and scale. DLT supports any type of data workload including batch and streaming with a single API.
   <img width="1664" height="900" alt="image" src="https://github.com/user-attachments/assets/8990c1b3-efc5-43f9-a8da-df9e64854f9a" />

   iii. Jobs - Helps to orchestrate everything within the platform for analytics and AI needs.
   <img width="1776" height="916" alt="image" src="https://github.com/user-attachments/assets/aefeefdb-7ba2-4a82-bd1c-98a253b7544f" />

 b. Databricks SQL
 c. AI/BI - Create dashboards on top of the data using natural language. ALso unity caltalog databases can be accessed easily on Power BI or Tableau.
     AI/BI Genie - Genie lets you go beyond dashboards. Talk to your data to explore any question.
 d. Mosaic AI
 <img width="873" height="749" alt="image" src="https://github.com/user-attachments/assets/2365e0cd-cb9e-429d-bedf-2bb73b3aed0c" />

 
3. Covered info on data warehouse, data lake, lakehouse, data intelligence. Its strengths and downsides.
4. Data swamp
5. Databricks architecture

<img width="1907" height="839" alt="image" src="https://github.com/user-attachments/assets/64957543-30af-4ffa-b0bb-e5ad976c00f8" />

<img width="1919" height="1030" alt="image" src="https://github.com/user-attachments/assets/2526950f-af9d-4579-a106-cbe9266255de" />

6. Databricks runs on top of cloud providers sugh as Azure, GCP, AWS.
7. Pillars for a well architected warehouse:
   a. Operational Excellence - All the operations that keep the lakehouse running in production.
   b. Security - Privacy or complaince that protect application and data from threats.
   c. Reliability - The ability of a system to recover from failures and can continue to function.
   d. Performance efficiency - The ability of a system to adapt to change in load.
   e. Cost optimization - Managing costs and maximize performance delivered.

   Lakehouse specific pillars:
   a. Data governance - Oversite to ensure that the data brings value and support to business strategy
   b. Interoperability and usability - For ensuring that the lakehouse has the ability to interact with users and other systems in the ecosystem.

8. Covered info on Mosaic AI, Databricks SQL, Workflows/DLT, Databricks AI/BI, AI/BI Genie, Unity Catalog, Delta lake, Iceberg, Parquet
9. Serverless compute scale dynamically preventing bottlenecks. Removes complexities in terms of managing infrastructure.
    <img width="1709" height="865" alt="image" src="https://github.com/user-attachments/assets/b8b03562-2a0a-40ae-988c-1204e9026fa6" />
    
10. Databricks Security and Governance
    Elements of data security and governance - Data cataloging, Data classification, Auditing data entitlements and access, data discovery, data sharing and collaboration, Data lineage, Data security, data quality. A good data governance strategy takes care of all of these areas.
    <img width="1753" height="914" alt="image" src="https://github.com/user-attachments/assets/c457a081-361b-4c31-9e21-078e80e58613" />

11. Challenges with data governance:
    a. Fragmented view of the data estate
    b. Multiple tools for access management
    c. Incomplete monitoring and visibility
    d. Lack of cross platform data sharing

12. Unity Catalog
    <img width="1780" height="968" alt="image" src="https://github.com/user-attachments/assets/ad5e6914-3d88-4e5f-855c-7301d65ae3c7" />
    Unity Catalog features:
    a. Define once, secure everywhere
    b. Standards - compliant security model
    c. Built in auditing and lineage
    d. Data and asset discovery
    e. System tables access

13. Databricks products and features
14. Model serving with databricks:
    a. Seamlessly integrates with MLflow model registry
    b. REST Endpoint allows for seamless integration with dashboards and external applications
    c. Delivers low latency, high throughput real time interface

15. Delta Sharing - It is an open cross platform sharing tool which allows easy sharing of delta, parquet or iceberg tables. Data is share live without copying it with data being maintained on the providers datalake ensuring the data is reliable in realtime. It avoids vendor lock in. It can also shre notebooks, ML models, Dashboards
<img width="734" height="697" alt="image" src="https://github.com/user-attachments/assets/cd7cd46e-40fb-442a-8643-77959f7edfbd" />

16. Databricks Marketplace - Open exchange for all data products like datasets, notebooks, dashboards, ML Models, solution accelerators. It is powered by delta sharing.
17. Databricks Workspace -
18. Databricks Notebooks
19. Catalog explorer
