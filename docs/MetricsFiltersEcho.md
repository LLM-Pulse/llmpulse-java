

# MetricsFiltersEcho

The filters the response was computed with, as the server resolved them. Each endpoint echoes only the keys it reads; a filter that was not given comes back null (or an empty list).

## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**metrics** | **List&lt;String&gt;** | Requested metrics after alias resolution (mention_rate is echoed as visibility) |  [optional] |
|**granularity** | **String** | day, week or month |  [optional] |
|**model** | **String** | The model filter, or null when absent or not enabled for the account |  [optional] |
|**collectionId** | **String** | The collection_id parameter as sent (one id or a comma-separated list) |  [optional] |
|**collectionIds** | **List&lt;Integer&gt;** |  |  [optional] |
|**domains** | **List&lt;String&gt;** |  |  [optional] |
|**countryCode** | **String** | Comma-separated country codes |  [optional] |
|**languageCode** | **String** | Comma-separated language codes |  [optional] |
|**prompt** | **Integer** | The prompt id filter |  [optional] |
|**promptType** | **String** | Comma-separated prompt types |  [optional] |
|**brandKind** | **String** |  |  [optional] |
|**competitors** | **List&lt;Integer&gt;** | Competitor ids from the competitors parameter; empty when it was not given |  [optional] |
|**includeProject** | **Boolean** |  |  [optional] |
|**query** | **String** | Only present when a query filter was given |  [optional] |



