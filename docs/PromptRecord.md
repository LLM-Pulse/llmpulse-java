

# PromptRecord


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  |
|**promptText** | **String** |  |  |
|**collectionId** | **Integer** | Primary tag, when the prompt has one |  |
|**collectionIds** | **List&lt;Integer&gt;** | Every tag the prompt belongs to |  |
|**tags** | [**List&lt;TagRef&gt;**](TagRef.md) |  |  |
|**countryCode** | **String** |  |  |
|**languageCode** | **String** |  |  |
|**promptType** | **String** | Search intent: informational, navigational, commercial or transactional. Null until the prompt is classified |  |
|**brandKind** | **String** | Brand focus: brand, brand_other or non_brand. Null until the prompt is classified |  |
|**lastExecutedAt** | **OffsetDateTime** | Null until the prompt has run |  |
|**appUrl** | **URI** | Opens this prompt in the app. The link names its project, so it opens there for any user with access to that project |  |



