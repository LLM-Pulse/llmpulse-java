

# CitedUrlOccurrencesResponseAllOfData


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**sourceId** | **Integer** |  |  |
|**answerId** | **Integer** |  |  |
|**promptExecutionId** | **Integer** | Same as answer_id |  |
|**promptId** | **Integer** |  |  |
|**promptText** | **String** |  |  |
|**model** | [**ModelEnum**](#ModelEnum) |  |  |
|**executedAt** | **OffsetDateTime** |  |  |
|**citationPosition** | **Integer** | Rank of the citation in the answer; 0 for a background source reference |  |
|**url** | **String** | Normalized cited URL |  |
|**domain** | **String** |  |  |
|**sourceType** | **String** | owned, competitor or third_party |  |
|**responseExcerpt** | **String** | The first 600 characters of the answer |  |
|**responseTruncated** | **Boolean** |  |  |
|**fanOutQueries** | **List&lt;String&gt;** | Sub-queries the model issued while answering; null when the model reports none |  |



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
| NAVER_AI_TAB | &quot;naver_ai_tab&quot; |
| QWEN | &quot;qwen&quot; |
| DOUBAO | &quot;doubao&quot; |
| BING_AI_MODE | &quot;bing_ai_mode&quot; |
| BING_AI_OVERVIEW | &quot;bing_ai_overview&quot; |



