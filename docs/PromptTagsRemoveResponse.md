

# PromptTagsRemoveResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  |
|**promptsTargeted** | **Integer** | Prompts of the project among prompt_ids |  |
|**tagsDetached** | [**List&lt;TagRef&gt;**](TagRef.md) |  |  |
|**linksRemoved** | **Integer** |  |  |
|**skippedNotLinked** | **Integer** |  |  |
|**missingTagNames** | **List&lt;String&gt;** | tag_names that matched no tag |  |
|**ignoredPromptIds** | **List&lt;Integer&gt;** | prompt_ids that are not prompts of this project |  |
|**requestId** | **String** |  |  |



