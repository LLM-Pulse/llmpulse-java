

# CustomReportSummary


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  |
|**name** | **String** |  |  |
|**dateRange** | [**CustomReportDateRange**](CustomReportDateRange.md) |  |  |
|**schedule** | [**CustomReportSchedule**](CustomReportSchedule.md) |  |  |
|**recipientsCount** | **Integer** |  |  |
|**published** | **Boolean** | Whether the shared link is published |  |
|**publicLinkActive** | **Boolean** | Whether the shared link opens (published, not made inside a client portal, and the account is active on the Scale tier or higher) |  |
|**passwordProtected** | **Boolean** |  |  |
|**portalOnly** | **Boolean** | Made inside a client portal, so it cannot be shared or emailed |  |
|**widgetCount** | **Integer** |  |  |
|**widgets** | [**List&lt;CustomReportWidgetRef&gt;**](CustomReportWidgetRef.md) |  |  |
|**lastSentAt** | **OffsetDateTime** | When the report was last emailed, on its schedule or with Send now |  [optional] |
|**createdAt** | **OffsetDateTime** |  |  |
|**updatedAt** | **OffsetDateTime** |  |  |



