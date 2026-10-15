

# OwnedMediaCitingPromptsResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  [optional] |
|**provider** | **String** |  |  [optional] |
|**from** | **OffsetDateTime** |  |  [optional] |
|**to** | **OffsetDateTime** |  |  [optional] |
|**item** | [**OwnedMediaCitedItem**](OwnedMediaCitedItem.md) |  |  [optional] |
|**citationCount** | **Integer** | Citations of the item in the window |  [optional] |
|**promptCount** | **Integer** | Distinct prompts whose answers cited it |  [optional] |
|**page** | **Integer** |  |  [optional] |
|**perPage** | **Integer** |  |  [optional] |
|**total** | **Integer** | Citing answers |  [optional] |
|**data** | [**List&lt;OwnedMediaCitingAnswer&gt;**](OwnedMediaCitingAnswer.md) |  |  [optional] |
|**requestId** | **String** |  |  [optional] |



