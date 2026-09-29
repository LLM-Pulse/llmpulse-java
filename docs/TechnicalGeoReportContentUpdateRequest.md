

# TechnicalGeoReportContentUpdateRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**reportType** | [**ReportTypeEnum**](#ReportTypeEnum) | Only llms_txt reports have editable content |  |
|**contentVersion** | **String** | result_data.content_version of the report as last read. It changes on every save; a value that no longer matches is refused as stale |  |
|**edits** | [**TechnicalGeoReportContentUpdateRequestEdits**](TechnicalGeoReportContentUpdateRequestEdits.md) |  |  |



## Enum: ReportTypeEnum

| Name | Value |
|---- | -----|
| LLMS_TXT | &quot;llms_txt&quot; |



