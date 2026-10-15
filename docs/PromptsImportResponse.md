

# PromptsImportResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**processedRows** | **Integer** | Distinct rows imported or matched to an existing prompt |  |
|**created** | **Integer** |  |  |
|**duplicates** | **Integer** | Rows that matched an existing prompt (they still get the row&#39;s tags) |  |
|**tagged** | **Integer** | New prompt-tag links |  |
|**createdTags** | **Integer** |  |  |
|**rowErrors** | [**List&lt;PromptsImportResponseRowErrorsInner&gt;**](PromptsImportResponseRowErrorsInner.md) | Rows that were skipped, by their index in rows |  |
|**lengthWarning** | **String** | Which tracked AI models will skip new prompts that are too long for them |  |
|**promptsAvailable** | **Integer** | Prompt slots left on the plan; null when unlimited |  |
|**requestId** | **String** |  |  |



