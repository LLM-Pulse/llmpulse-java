

# PromptTagsAssignResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**promptsTargeted** | **Integer** | Prompts of the project among prompt_ids |  |
|**tagsAttached** | [**List&lt;TagRef&gt;**](TagRef.md) |  |  |
|**newLinksCreated** | **Integer** |  |  |
|**skippedAlreadyLinked** | **Integer** |  |  |
|**missingTagNames** | **List&lt;String&gt;** | tag_names that matched no tag and were not created |  |
|**ignoredPromptIds** | **List&lt;Integer&gt;** | prompt_ids that are not prompts of this project |  |
|**requestId** | **String** |  |  |



