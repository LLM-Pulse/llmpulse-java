

# PromptsCreateResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  [optional] |
|**created** | **Integer** |  |  [optional] |
|**skipped** | **Integer** |  |  [optional] |
|**totalAfter** | **Integer** |  |  [optional] |
|**promptsAvailable** | **Integer** |  |  [optional] |
|**tracked** | **Boolean** | Whether scheduled runs include the project the prompts were added to. False when it is paused or beyond the plan&#39;s project limit, so the new prompts do not run until that changes |  [optional] |
|**untrackedReason** | **String** | Why tracked is false: paused or project_limit. Null when tracked |  [optional] |
|**warning** | **String** | What to do when tracked is false. Null when tracked |  [optional] |
|**data** | [**List&lt;PromptsCreateResponseDataInner&gt;**](PromptsCreateResponseDataInner.md) |  |  [optional] |
|**requestId** | **String** |  |  [optional] |



