

# CustomReportDetailResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**id** | **Integer** |  |  |
|**name** | **String** |  |  |
|**dateRange** | [**CustomReportDateRange**](CustomReportDateRange.md) |  |  |
|**schedule** | [**CustomReportSchedule**](CustomReportSchedule.md) |  |  |
|**recipientsCount** | **Integer** |  |  [optional] |
|**published** | **Boolean** |  |  [optional] |
|**publicLinkActive** | **Boolean** |  |  [optional] |
|**passwordProtected** | **Boolean** |  |  [optional] |
|**portalOnly** | **Boolean** |  |  [optional] |
|**lastSentAt** | **OffsetDateTime** | When the report was last emailed, on its schedule or with Send now |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  [optional] |
|**updatedAt** | **OffsetDateTime** |  |  [optional] |
|**filters** | [**CustomReportFilters**](CustomReportFilters.md) |  |  |
|**comparePrevious** | **Boolean** |  |  [optional] |
|**attachExcel** | **Boolean** |  |  [optional] |
|**manualSendAvailableAt** | **OffsetDateTime** | When the 10-minute cooldown after the last manual send ends; null when none is running |  [optional] |
|**generatedAt** | **OffsetDateTime** |  |  |
|**blocks** | [**List&lt;CustomReportBlock&gt;**](CustomReportBlock.md) | The report layout in order |  |
|**widgets** | [**List&lt;CustomReportWidget&gt;**](CustomReportWidget.md) |  |  |
|**requestId** | **String** |  |  |



