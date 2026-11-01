

# ProjectDetailsAllOfPitchRun

The one run of a pitch project; null for a tracked project. Its answers are dated between launched_at and settled_at, so read its metrics with from set to the launched_at date (the default ranges leave out a pitch older than a few weeks)

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**status** | [**StatusEnum**](#StatusEnum) | starting before the run begins, running while answers arrive, ready once every AI model has answered or stopped trying |  [optional] |
|**launchedAt** | **OffsetDateTime** |  |  [optional] |
|**settledAt** | **OffsetDateTime** |  |  [optional] |
|**models** | [**List&lt;ModelsEnum&gt;**](#List&lt;ModelsEnum&gt;) | The AI models the run asks, fixed when it starts |  [optional] |
|**answersExpected** | **Integer** |  |  [optional] |
|**answersReceived** | **Integer** |  |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| STARTING | &quot;starting&quot; |
| RUNNING | &quot;running&quot; |
| READY | &quot;ready&quot; |



## Enum: List&lt;ModelsEnum&gt;

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



