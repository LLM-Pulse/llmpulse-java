

# PromptsImportResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**processedRows** | **Integer** | Distinct rows imported or matched to an existing prompt |  |
|**created** | **Integer** |  |  |
|**duplicates** | **Integer** | Rows that matched an existing prompt (they still get the row&#39;s tags, unless a team member lacks update access to Prompts) |  |
|**tagged** | **Integer** | New prompt-tag links |  |
|**createdTags** | **Integer** |  |  |
|**rowErrors** | [**List&lt;PromptsImportResponseRowErrorsInner&gt;**](PromptsImportResponseRowErrorsInner.md) | Rows that were skipped or whose tags were not added, by their index in rows |  |
|**lengthWarning** | **String** | Which tracked AI models will skip new prompts that are too long for them |  |
|**promptsAvailable** | **Integer** | Prompt slots left on the plan; null when unlimited |  |
|**tracked** | **Boolean** | Whether scheduled runs include the project the prompts were imported into. False when it is paused or beyond the plan&#39;s project limit, so the new prompts do not run until that changes |  |
|**untrackedReason** | **String** | Why tracked is false: pitch_project, paused or project_limit. Null when tracked |  |
|**warning** | **String** | What to do when tracked is false, or why some first runs wait when first_runs_wait_until is set. Null otherwise |  |
|**firstRunsWaitUntil** | **OffsetDateTime** | Set when the account&#39;s allowance of AI answers left this cycle, or the project&#39;s own share of it when the account caps each project&#39;s executions, cannot give every new prompt one answer per enabled AI model, so the rest run when the allowance resets at this time (00:00 Europe/Madrid). It counts this request&#39;s prompts against what was left when it arrived, not first runs other requests queued moments earlier. Null otherwise, when the allowance is unlimited, when tracked is false or when the account is not active |  |
|**requestId** | **String** |  |  |



