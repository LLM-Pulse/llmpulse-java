

# PromptGenerationResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **UUID** | The run id; poll GET /prompt_generations/{id} with it (kept for 24 hours) |  |
|**projectId** | **Integer** |  |  |
|**source** | **String** |  |  |
|**status** | [**StatusEnum**](#StatusEnum) |  |  |
|**params** | [**PromptGenerationResponseParams**](PromptGenerationResponseParams.md) |  |  |
|**createdAt** | **OffsetDateTime** |  |  |
|**finishedAt** | **OffsetDateTime** |  |  |
|**suggestionsCount** | **Integer** |  |  |
|**suggestions** | [**List&lt;SuggestedPrompt&gt;**](SuggestedPrompt.md) | The suggestions the run saved to the Suggested prompts queue, with their current status |  |
|**error** | [**PromptGenerationResponseError**](PromptGenerationResponseError.md) |  |  |
|**requestId** | **String** |  |  |



## Enum: StatusEnum

| Name | Value |
|---- | -----|
| PROCESSING | &quot;processing&quot; |
| COMPLETED | &quot;completed&quot; |
| FAILED | &quot;failed&quot; |



