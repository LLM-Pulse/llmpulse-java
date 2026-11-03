

# AiModelInsightsFiltersEcho

The filters the summary was computed with, as the server resolved them. A filter that was not given is left out, except granularity and competitors.

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**from** | **OffsetDateTime** |  |  [optional] |
|**to** | **OffsetDateTime** |  |  [optional] |
|**granularity** | **String** | day, week or month; day when not given |  [optional] |
|**countryCode** | **String** | Comma-separated country codes |  [optional] |
|**languageCode** | **String** | Comma-separated language codes |  [optional] |
|**collectionId** | **String** | Comma-separated collection ids |  [optional] |
|**promptType** | **String** | Comma-separated prompt types |  [optional] |
|**brandKind** | **String** |  |  [optional] |
|**competitors** | **List&lt;Integer&gt;** | Competitor ids from the competitors parameter; empty when it was not given |  [optional] |



