

# ReputationReportSummary

One reputation report's status and analyst model coverage

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **String** | Report id for GET /reputation/reports/{id} |  |
|**status** | [**StatusEnum**](#StatusEnum) |  |  |
|**createdAt** | **OffsetDateTime** |  |  |
|**processedAt** | **OffsetDateTime** |  |  [optional] |
|**availableModels** | [**List&lt;AvailableModelsEnum&gt;**](#List&lt;AvailableModelsEnum&gt;) | Analyst models that produced data |  |
|**missingModels** | [**List&lt;MissingModelsEnum&gt;**](#List&lt;MissingModelsEnum&gt;) | Analyst models with no data yet |  |
|**errorMessage** | **String** | Why the report failed; null unless status is failed |  [optional] |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| PENDING | &quot;pending&quot; |
| PROCESSING | &quot;processing&quot; |
| COMPLETED | &quot;completed&quot; |
| FAILED | &quot;failed&quot; |



## Enum: List&lt;AvailableModelsEnum&gt;

| Name | Value |
|---- | -----|
| CHATGPT | &quot;chatgpt&quot; |
| PERPLEXITY | &quot;perplexity&quot; |
| GEMINI | &quot;gemini&quot; |
| DEEPSEEK | &quot;deepseek&quot; |
| GROK | &quot;grok&quot; |
| CLAUDE | &quot;claude&quot; |



## Enum: List&lt;MissingModelsEnum&gt;

| Name | Value |
|---- | -----|
| CHATGPT | &quot;chatgpt&quot; |
| PERPLEXITY | &quot;perplexity&quot; |
| GEMINI | &quot;gemini&quot; |
| DEEPSEEK | &quot;deepseek&quot; |
| GROK | &quot;grok&quot; |
| CLAUDE | &quot;claude&quot; |



