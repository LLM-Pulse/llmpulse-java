

# AiModelDeclinedAnswersResponse

How often one AI model declined to answer the project's prompts. An answer is a finished run of the model, a declined one included; a declined answer counts as no answer and never enters the metrics. The window starts at the tracking period holding its first day, and summary, chart and by_prompt count that same window.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**from** | **OffsetDateTime** | Start of the tracking period holding the first day asked for |  |
|**to** | **OffsetDateTime** |  |  |
|**model** | [**ModelEnum**](#ModelEnum) | The model the counts are for |  |
|**cadence** | **String** | The account&#39;s current tracking cadence: daily, weekly or monthly. Chart periods before a switch from weekly to daily stay weekly. |  |
|**filters** | [**AiModelDeclinedAnswersResponseFilters**](AiModelDeclinedAnswersResponseFilters.md) |  |  [optional] |
|**summary** | [**AiModelDeclinedAnswersResponseSummary**](AiModelDeclinedAnswersResponseSummary.md) |  |  |
|**chart** | [**List&lt;AiModelDeclinedAnswersResponseChartInner&gt;**](AiModelDeclinedAnswersResponseChartInner.md) | One point per tracking period holding an answer, oldest first. A period without answers has no point; a period with answers and no declines is a real 0. |  |
|**byPrompt** | [**AiModelDeclinedAnswersResponseByPrompt**](AiModelDeclinedAnswersResponseByPrompt.md) |  |  |
|**requestId** | **String** |  |  [optional] |



## Enum: ModelEnum

| Name | Value |
|---- | -----|
| GEMINI | &quot;gemini&quot; |



