

# AdRow

One row of /dimensions/ads. Fields depend on view: advertisers (domain, ads, executions, prompts, avg_position, best_position) and ads (id, model, title, snippet, url, domain, position, is_client, prompt_id, prompt_text, prompt_execution_id, executed_at).

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**domain** | **String** | Advertising domain; null on a placement that names none (view&#x3D;ads) |  |
|**ads** | **Integer** | Placements of the domain (view&#x3D;advertisers) |  [optional] |
|**executions** | **Integer** | Answers that carried them (view&#x3D;advertisers) |  [optional] |
|**prompts** | **Integer** | Distinct prompts that triggered them (view&#x3D;advertisers) |  [optional] |
|**avgPosition** | **BigDecimal** | Average position, 1 is the best slot; null when no placement has one (view&#x3D;advertisers) |  [optional] |
|**bestPosition** | **Integer** | Best position, 1 is the best slot (view&#x3D;advertisers) |  [optional] |
|**id** | **Integer** | The placement (view&#x3D;ads) |  [optional] |
|**model** | [**ModelEnum**](#ModelEnum) |  |  [optional] |
|**title** | **String** |  |  [optional] |
|**snippet** | **String** |  |  [optional] |
|**url** | **String** |  |  [optional] |
|**position** | **Integer** | Position of the placement, 1 is the best slot (view&#x3D;ads) |  [optional] |
|**isClient** | **Boolean** | Whether the placement is identified as your brand&#39;s own (view&#x3D;ads) |  [optional] |
|**promptId** | **Integer** |  |  [optional] |
|**promptText** | **String** |  |  [optional] |
|**promptExecutionId** | **Integer** |  |  [optional] |
|**executedAt** | **OffsetDateTime** | When the answer that carried the placement was collected (view&#x3D;ads) |  [optional] |



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



