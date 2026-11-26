

# CitationSeries

The answers citing it under the same filters, by AI model and per period of the account tracking cadence

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**granularity** | [**GranularityEnum**](#GranularityEnum) |  |  |
|**total** | **Integer** | Equal to total_responses |  |
|**byModel** | **Map&lt;String, Integer&gt;** | Answers per AI model, keyed by model, largest first |  |
|**data** | [**List&lt;AiModelPositionDistributionBrandBucketsInnerDataInner&gt;**](AiModelPositionDistributionBrandBucketsInnerDataInner.md) | One point per period holding a filtered answer, oldest first; a zero means answers ran and none cited it |  |



## Enum: GranularityEnum

| Name | Value |
|---- | -----|
| DAY | &quot;day&quot; |
| WEEK | &quot;week&quot; |
| MONTH | &quot;month&quot; |



