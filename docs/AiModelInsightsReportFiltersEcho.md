

# AiModelInsightsReportFiltersEcho

The filters a position distribution or AI Overview report was computed with, as the server resolved them. A filter that was not given is left out, except from, to, granularity and competitors.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**from** | **OffsetDateTime** |  |  |
|**to** | **OffsetDateTime** |  |  |
|**granularity** | [**GranularityEnum**](#GranularityEnum) |  |  |
|**countryCode** | **String** | Comma-separated country codes |  [optional] |
|**languageCode** | **String** | Comma-separated language codes |  [optional] |
|**collectionId** | **String** | Comma-separated collection ids |  [optional] |
|**promptType** | **String** | Comma-separated prompt types |  [optional] |
|**brandKind** | **String** |  |  [optional] |
|**model** | [**ModelEnum**](#ModelEnum) | The model filter; always ai_overview on the AI Overview report |  [optional] |
|**competitors** | **List&lt;Integer&gt;** | Competitor ids from the competitors parameter; empty when it was not given |  |
|**brand1** | **String** | Position distribution only. The id, as a string, of the competitor compared as the first brand; left out for the project brand |  [optional] |
|**brand2** | **String** | Position distribution only. The id, as a string, of the competitor compared as the second brand, by default the competitor with the most mentions; left out when the project has none to compare |  [optional] |



## Enum: GranularityEnum

| Name | Value |
|---- | -----|
| DAY | &quot;day&quot; |
| WEEK | &quot;week&quot; |
| MONTH | &quot;month&quot; |



## Enum: ModelEnum

| Name | Value |
|---- | -----|
| CHATGPT | &quot;chatgpt&quot; |
| AI_MODE | &quot;ai_mode&quot; |
| AI_OVERVIEW | &quot;ai_overview&quot; |
| PERPLEXITY | &quot;perplexity&quot; |
| GEMINI | &quot;gemini&quot; |
| NAVER_AI | &quot;naver_ai&quot; |
| BAIDU_AI | &quot;baidu_ai&quot; |
| NAVER_AI_TAB | &quot;naver_ai_tab&quot; |
| QWEN | &quot;qwen&quot; |
| DOUBAO | &quot;doubao&quot; |
| BING_AI_MODE | &quot;bing_ai_mode&quot; |
| BING_AI_OVERVIEW | &quot;bing_ai_overview&quot; |



