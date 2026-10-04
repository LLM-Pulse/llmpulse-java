

# CatalogPromptSuggestion


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Integer** |  |  |
|**prompt** | **String** |  |  |
|**status** | **String** | pending, accepted or rejected |  |
|**source** | **String** | Always catalog |  |
|**countryCode** | **String** |  |  |
|**languageCode** | **String** |  |  |
|**product** | [**CatalogPromptSuggestionProduct**](CatalogPromptSuggestionProduct.md) |  |  |
|**promptId** | **Integer** | The tracked prompt an accepted suggestion became; null until accepted |  |
|**acceptedAt** | **OffsetDateTime** | When the suggestion was accepted; null until then |  |
|**createdAt** | **OffsetDateTime** |  |  |



