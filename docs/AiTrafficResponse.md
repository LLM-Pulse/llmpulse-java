

# AiTrafficResponse

Visits from AI assistants measured by the connected web analytics provider, by day over the window.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**provider** | **String** | The connected provider: google_analytics, adobe_analytics, adobe_cja, posthog, plausible, matomo or piano |  |
|**from** | **LocalDate** |  |  |
|**to** | **LocalDate** |  |  |
|**granularity** | [**GranularityEnum**](#GranularityEnum) |  |  |
|**totals** | [**AiTrafficResponseTotals**](AiTrafficResponseTotals.md) |  |  |
|**bySource** | [**List&lt;AiTrafficResponseBySourceInner&gt;**](AiTrafficResponseBySourceInner.md) | One row per AI source with traffic in the window, most sessions first |  |
|**timeseries** | **Map&lt;String, Map&lt;String, Integer&gt;&gt;** | Sessions keyed by AI source slug, then by the first day of the period (YYYY-MM-DD); a period without traffic is left out |  |
|**requestId** | **String** |  |  |



## Enum: GranularityEnum

| Name | Value |
|---- | -----|
| DAY | &quot;day&quot; |
| WEEK | &quot;week&quot; |
| MONTH | &quot;month&quot; |



