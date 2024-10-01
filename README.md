
# Stream Analytics Project
Storage Diagnostic Logs Analytics

![image](https://github.com/user-attachments/assets/17818a54-e908-4415-88af-a60671adaa8c)


### Overview
This project demonstrates the deployment and integration of Azure Synapse, Event Hub, and Azure Stream Analytics to process and analyze streaming data from Azure Data Lake Gen2. The goal is to create a seamless pipeline that ingests diagnostic logs, processes them in real-time, and stores the results in a dedicated SQL pool for further analysis.

#### Project Goal
The primary goal of this project is to set up a robust data pipeline that:
1. Streams diagnostic logs from Azure Data Lake Gen2 to Event Hub.
2. Processes the streaming data using Azure Stream Analytics.
3. Stores the processed data in Azure Synapse Dedicated SQL Pool for analysis.

## Phase 1: Setting Up Resources

### Create Azure Event Hub
- **Navigate to Azure Portal**: Go to the Azure portal and create a new Event Hub namespace.
- **Create Event Hub Instance**: Within the namespace, create an Event Hub instance to receive streaming data.

### Enable Diagnostic Settings for Data Lake Gen2
- **Enable Diagnostic Logs**: Enable diagnostic settings for your Azure Data Lake Gen2 account to stream logs to Event Hub.
- **Select Metrics**: Choose the specific metrics and logs you want to monitor and stream.

## Phase 2: Configuring Azure Stream Analytics

### Create Stream Analytics Job
- **Create Job**: In the Azure portal, create a new Stream Analytics job.
- **Input Configuration**: Define Event Hub as the input source for the Stream Analytics job.

### Define Output to Azure Synapse
- **Create Output**: Configure the output of the Stream Analytics job to point to your Azure Synapse Dedicated SQL Pool.
- **Staging Storage**: Set up a Storage Account as staging storage for intermediate data processing.

## Phase 3: Preparing Azure Synapse Analytics

### Create Dedicated SQL Pool
- **Create Table**: In Azure Synapse Analytics, create a table in the Dedicated SQL Pool to store the incoming data from Stream Analytics.

## Phase 4: Querying and Processing Data

### Write Stream Analytics Query
- **Define Query**: Write a query to process the JSON stream data. Use techniques like `CROSS APPLY` and `GetArrayElement` to extract required columns.
- **Test Query**: Validate the query to ensure it extracts the necessary data correctly.

### Run Stream Analytics Job
- **Start Job**: Run the Stream Analytics job and monitor its progress.
- **Verify Data**: Check the data in Azure Synapse to ensure it is correctly ingested into the table.

## Phase 5: Final Testing and Validation

### Validate Data in Synapse
- **Query Data**: Run queries in Azure Synapse to verify that the data is correctly stored and accessible.
- **Analyze Results**: Ensure the data meets the expected format and content requirements.

## Power BI (Visualisation)

![image](https://github.com/user-attachments/assets/e7d15a1a-5d79-47aa-a457-140566e6f430)


