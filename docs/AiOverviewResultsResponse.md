

# AiOverviewResultsResponse

How often Google AI Overviews returned a result for the project's prompts. A result rate is a percentage (0-100) of the AI Overview runs, 0 when there is none.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**from** | **OffsetDateTime** |  |  |
|**to** | **OffsetDateTime** |  |  |
|**filters** | [**AiModelInsightsReportFiltersEcho**](AiModelInsightsReportFiltersEcho.md) |  |  |
|**granularity** | [**GranularityEnum**](#GranularityEnum) |  |  |
|**summary** | [**AiOverviewResultCounts**](AiOverviewResultCounts.md) |  |  |
|**chart** | [**List&lt;AiOverviewResultsResponseChartInner&gt;**](AiOverviewResultsResponseChartInner.md) | One point per period of the window, oldest first, 0 included |  |
|**byPrompt** | [**AiOverviewResultsResponseByPrompt**](AiOverviewResultsResponseByPrompt.md) |  |  |
|**requestId** | **String** |  |  |



## Enum: GranularityEnum

| Name | Value |
|---- | -----|
| DAY | &quot;day&quot; |
| WEEK | &quot;week&quot; |
| MONTH | &quot;month&quot; |



