

# AnswerRecord

One answer. Without query a row carries response and response_truncated; with query it carries snippet and match_count instead

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  |
|**promptId** | **Integer** |  |  |
|**promptText** | **String** |  |  |
|**model** | [**ModelEnum**](#ModelEnum) |  |  |
|**executedAt** | **OffsetDateTime** |  |  |
|**durationMs** | **BigDecimal** | Milliseconds our pipeline spent processing the collected answer, rounded to one decimal place |  |
|**noResult** | **Boolean** | True for a sentinel non-answer (no answer could be collected after all retries, or the model declined to answer, today only Gemini); excluded from platform metrics |  |
|**noResultReason** | [**NoResultReasonEnum**](#NoResultReasonEnum) | Present only when no_result is true. declined &#x3D; the model declined to answer and response holds its reply; no_answer &#x3D; no answer could be collected |  [optional] |
|**mentionsCount** | **Integer** | Mentions of your brand in the answer |  |
|**citationsCount** | **Integer** | Citations of your brand in the answer |  |
|**appUrl** | **URI** | Opens this answer in the app. The link names its project, so it opens there for any user with access to that project |  |
|**response** | **String** | The answer text, cut to 10,000 characters (without query) |  [optional] |
|**responseTruncated** | **Boolean** | Whether response was cut (without query) |  [optional] |
|**snippet** | **String** | The text around the first match (with query) |  [optional] |
|**matchCount** | **Integer** | Matches of query in the answer (with query) |  [optional] |



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



## Enum: NoResultReasonEnum

| Name | Value |
|---- | -----|
| DECLINED | &quot;declined&quot; |
| NO_ANSWER | &quot;no_answer&quot; |



