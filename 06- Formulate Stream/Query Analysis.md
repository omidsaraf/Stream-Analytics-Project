We can read the data easily in two modes: as a Table or extract the raw data in its original format. Most of the data that streams into Event Hub comes as arrays, which need to be broken down in the query to extract the information within them.
- Arrays start with [ and the objects within them start with {.
- Whenever an object ends, i.e., }, the first record ends with a comma, and the next record begins."


![image](https://github.com/user-attachments/assets/d3d7b299-e43c-4700-b996-a4619fd8b6e0)


For our JSON file that comes as a stream from the Storage Diagnostic Log, we need to create a query as follows:
- Specify the source and destination
- Use Cross Apply and Get Array Element
- Specify the Dataset (reference)
- Analyze the elements we want to fetch
- Specify each element and its belonging layer for writing the SELECT columns

![image](https://github.com/user-attachments/assets/d831c5b3-e69e-4e57-a1fa-a75eaed30db6)

````sql
SELECT 
    Records.ArrayValue.category AS Category,
    Records.ArrayValue.operationName AS OperationName,
    Records.ArrayValue.statusText AS StatusText,
    Records.ArrayValue.properties.objectkey AS ObjectKey,
    Records.ArrayValue.[identity].type AS IdentityType,
    Records.ArrayValue.[identity].tokenHash AS TokenHash
INTO 
    BlobDiagnostics
FROM 
    [blobhub] bh
CROSS APPLY 
    GetArrayElements(bh.records) AS Records;
