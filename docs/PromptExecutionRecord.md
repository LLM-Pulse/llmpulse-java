

# PromptExecutionRecord


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  |
|**promptId** | **Integer** |  |  |
|**executedAt** | **OffsetDateTime** | Null while the answer is still pending |  |
|**durationMs** | **BigDecimal** |  |  |
|**success** | **Boolean** | Null while the answer is still pending |  |
|**model** | [**ModelEnum**](#ModelEnum) |  |  |
|**fanOutQueries** | **List&lt;String&gt;** | Sub-queries the model issued while answering; null when the model reports none |  |
|**hasMention** | **Boolean** |  |  |
|**hasCitation** | **Boolean** |  |  |
|**mentionsCount** | **Integer** | 1 when the answer mentions the brand, otherwise 0 |  |
|**citationsCount** | **Integer** | 1 when the answer cites the brand, otherwise 0 |  |
|**appUrl** | **URI** | Opens this answer in the app. The link names its project, so it opens there for any user with access to that project |  |



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



