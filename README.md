# azure_data_factory_project_orders

Stage 1: 
- I have ingested the data from landing zome to the raw file using copyData activity on ADF
- Transformed the data by adding the required columns using derived columns, cast feature, drop columns and sink activity to store the transformed dataset
- Finally, I have built the execute pipeline to trigger the transformation datapipeline from RawToCleansed, CleansedToStructured and as adhoc StructuredToAnalytics based on requirement from the team with whom I am working with

Stage 2:
- In stage 2, I have implement folder generation using @concat('customers/', formatDateTime(utcNow(), 'yyyy-MM-dd')) using dynamic content
- The above is not the optimized solution or the complete solution so to analyse, in the above solution we get a duplicate date content and it is a bit complex approach for me to go with solving the duplicate data copy in the Stage 2 solution.
- I am thinking of creating the Stage 3 to solve the duplication problem using UPSERT.

Stage 3:
- Using SQL for the sink Copy Activity and Dataflows
- We can use the SQL database quick editor to query the tables saved in sink
