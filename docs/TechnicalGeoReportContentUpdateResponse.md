

# TechnicalGeoReportContentUpdateResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  [optional] |
|**reportType** | **String** | Always llms_txt |  [optional] |
|**projectId** | **Integer** |  |  [optional] |
|**batchId** | **Integer** | Bundle the report was created in; null for a report created on its own |  [optional] |
|**url** | **String** | Always null for llms_txt reports; domain names the website |  [optional] |
|**domain** | **String** |  |  [optional] |
|**countryCode** | **String** |  |  [optional] |
|**outputLanguageCode** | **String** | ISO 639-1 code the files were requested in; null when they are written in the website&#39;s own language |  [optional] |
|**status** | **String** |  |  [optional] |
|**resultAvailable** | **Boolean** |  |  [optional] |
|**overallScore** | **BigDecimal** | Always null for llms_txt reports |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  [optional] |
|**updatedAt** | **OffsetDateTime** |  |  [optional] |
|**resultData** | [**LlmsTxtTechnicalGeoReportResultData**](LlmsTxtTechnicalGeoReportResultData.md) |  |  [optional] |
|**errorMessage** | **String** |  |  [optional] |
|**pollAfterSeconds** | **Integer** | Seconds to wait before polling again while the report runs; null once it has finished |  [optional] |
|**appUrl** | **URI** | Opens this report in the app |  [optional] |
|**requestId** | **String** |  |  [optional] |
|**changedFiles** | [**List&lt;ChangedFilesEnum&gt;**](#List&lt;ChangedFilesEnum&gt;) | Files whose text actually changed; empty when every file matched the stored text |  [optional] |



## Enum: List&lt;ChangedFilesEnum&gt;

| Name | Value |
|---- | -----|
| LLMS_TXT | &quot;llms_txt&quot; |
| LLMS_FULL_TXT | &quot;llms_full_txt&quot; |



