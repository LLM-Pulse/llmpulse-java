

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
|**untrackedReason** | **String** | Why tracked is false: pitch_project, paused or project_limit. Null when tracked |  [optional] |
|**warning** | **String** | What to do when tracked is false, or why some first runs wait when first_runs_wait_until is set. Null otherwise |  [optional] |
|**firstRunsWaitUntil** | **OffsetDateTime** | Set when the account&#39;s allowance of AI answers left this cycle cannot give every new prompt one answer per enabled AI model, so the rest run when the allowance resets at this time (00:00 Europe/Madrid). It counts this request&#39;s prompts against what was left when it arrived, not first runs other requests queued moments earlier. Null otherwise, when the allowance is unlimited, when tracked is false or when the account is not active |  [optional] |
|**data** | [**List&lt;PromptsCreateResponseDataInner&gt;**](PromptsCreateResponseDataInner.md) |  |  [optional] |
|**requestId** | **String** |  |  [optional] |



