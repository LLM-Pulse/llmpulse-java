

# StudyResponse

One custom AI study with its brief, subjects, dimensions and latest reports

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  |
|**title** | **String** |  |  |
|**studyType** | **String** | brand_set, sector, geo, topic or custom |  |
|**cadence** | **String** | one_shot or monthly |  |
|**status** | **String** | active or archived |  |
|**projectId** | **Integer** | The project the study is attached to; null for an account-level study |  |
|**subjectsCount** | **Integer** |  |  |
|**aiModels** | [**List&lt;AiModelsEnum&gt;**](#List&lt;AiModelsEnum&gt;) | Analyst models the study runs on |  |
|**outputLanguageCode** | **String** | ISO 639-1 code of the language the reports are written in |  |
|**createdAt** | **OffsetDateTime** |  |  |
|**lastReportAt** | **OffsetDateTime** | When the latest report started; null before the first one |  |
|**brief** | **String** | What the study asks the analyst models; null when none was written |  |
|**subjects** | **List&lt;String&gt;** | Names of the subjects it compares |  |
|**dimensions** | **List&lt;String&gt;** | Keys of the dimensions it scores, as the dimension filter takes them |  |
|**reports** | [**List&lt;ReputationReportSummary&gt;**](ReputationReportSummary.md) | The 24 latest reports, newest first |  |
|**requestId** | **String** |  |  |



## Enum: List&lt;AiModelsEnum&gt;

| Name | Value |
|---- | -----|
| CHATGPT | &quot;chatgpt&quot; |
| PERPLEXITY | &quot;perplexity&quot; |
| GEMINI | &quot;gemini&quot; |
| DEEPSEEK | &quot;deepseek&quot; |
| GROK | &quot;grok&quot; |
| CLAUDE | &quot;claude&quot; |



