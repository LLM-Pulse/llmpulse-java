

# SentimentRecord


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  |
|**promptExecutionId** | **Integer** |  |  |
|**promptText** | **String** |  |  |
|**model** | [**ModelEnum**](#ModelEnum) |  |  |
|**analysis** | [**AnalysisEnum**](#AnalysisEnum) |  |  |
|**score** | **BigDecimal** | From -1 (very negative) to 1 (very positive) |  |
|**comment** | **String** |  |  |
|**topics** | **String** | Comma-separated topics |  |
|**competitorId** | **Integer** | Null for a sentiment about the project&#39;s own brand |  |
|**competitorName** | **String** | Null for a sentiment about the project&#39;s own brand |  |
|**isBrandSentiment** | **Boolean** |  |  |
|**executedAt** | **OffsetDateTime** |  |  |
|**createdAt** | **OffsetDateTime** |  |  |



## Enum: ModelEnum

| Name | Value |
|---- | -----|
| CHATGPT | &quot;chatgpt&quot; |
| PERPLEXITY | &quot;perplexity&quot; |
| AI_MODE | &quot;ai_mode&quot; |
| AI_OVERVIEW | &quot;ai_overview&quot; |
| GEMINI | &quot;gemini&quot; |
| COPILOT | &quot;copilot&quot; |
| AMAZON_RUFUS | &quot;amazon_rufus&quot; |
| CLAUDE | &quot;claude&quot; |
| GROK | &quot;grok&quot; |
| DEEPSEEK | &quot;deepseek&quot; |
| NAVER_AI | &quot;naver_ai&quot; |
| BAIDU_AI | &quot;baidu_ai&quot; |
| META_AI | &quot;meta_ai&quot; |



## Enum: AnalysisEnum

| Name | Value |
|---- | -----|
| VERY_POSITIVE | &quot;very_positive&quot; |
| POSITIVE | &quot;positive&quot; |
| NEUTRAL | &quot;neutral&quot; |
| NEGATIVE | &quot;negative&quot; |
| VERY_NEGATIVE | &quot;very_negative&quot; |



