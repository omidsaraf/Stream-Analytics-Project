

In Azure, every resource we use includes a service called Diagnostic Settings, which streams data related to that resource in JSON format and includes various metrics. The Azure Storage Account, as a resource, also has this service, and we want to use it as stream data.

Since the Storage Account consists of four sections, we only want to have Diagnostic Logs for Blob Storage, so we select it. On the displayed page, we can obtain information about operations related to that specific resource through this Diagnostic Log. One of its features is Anomaly Detection, and it also shows who has attempted to access the service.
