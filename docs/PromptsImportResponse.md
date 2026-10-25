

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
|**untrackedReason** | **String** | Why tracked is false: paused or project_limit. Null when tracked |  |
|**warning** | **String** | What to do when tracked is false. Null when tracked |  |
|**requestId** | **String** |  |  |



