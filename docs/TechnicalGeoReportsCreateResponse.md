

# TechnicalGeoReportsCreateResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**url** | **String** | The URL analysed |  |
|**countryCode** | **String** | The country used, the project country when none was sent |  |
|**outputLanguageCode** | **String** | ISO 639-1 code the llms.txt files are written in, or auto for the website&#39;s own language |  |
|**batchId** | **Integer** | Bundle id, for the batch_id filter of GET /technical_geo_reports; null when no report was created |  |
|**createdReports** | **List&lt;String&gt;** | The report_type of every report created |  |
|**reportIds** | **Map&lt;String, Integer&gt;** | The id of each created report, by report_type |  |
|**appUrls** | **Map&lt;String, URI&gt;** | The link that opens each created report in the app, by report_type |  |
|**failedReports** | [**List&lt;TechnicalGeoReportsCreateResponseFailedReportsInner&gt;**](TechnicalGeoReportsCreateResponseFailedReportsInner.md) | Reports that could not be created, with the reasons |  |
|**nextEndpoint** | **String** | Path template to poll each created report |  |
|**pollAfterSeconds** | **Integer** | Seconds to wait before the first poll |  |
|**requestId** | **String** |  |  |



