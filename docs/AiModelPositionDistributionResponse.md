

# AiModelPositionDistributionResponse

The positions at which one or two brands were mentioned, in four buckets, per period of the window.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**from** | **OffsetDateTime** |  |  |
|**to** | **OffsetDateTime** |  |  |
|**filters** | [**AiModelInsightsReportFiltersEcho**](AiModelInsightsReportFiltersEcho.md) |  |  |
|**granularity** | [**GranularityEnum**](#GranularityEnum) |  |  |
|**brands** | [**List&lt;AiModelPositionDistributionBrand&gt;**](AiModelPositionDistributionBrand.md) | The first brand (brand1, else the project) and the second (brand2, else the competitor with the most mentions, else the project), each left out when it has no mention in the window |  |
|**maxStackedValue** | **Integer** | The largest mentions count of one period across the brands, for a shared chart axis |  |
|**requestId** | **String** |  |  |



## Enum: GranularityEnum

| Name | Value |
|---- | -----|
| DAY | &quot;day&quot; |
| WEEK | &quot;week&quot; |
| MONTH | &quot;month&quot; |



