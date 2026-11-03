

# SearchConsoleAiVisibilityGapsResponse


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**projectId** | **Integer** |  |  [optional] |
|**property** | [**SearchConsoleProperty**](SearchConsoleProperty.md) |  |  [optional] |
|**properties** | [**List&lt;SearchConsoleProperty&gt;**](SearchConsoleProperty.md) | With a list or all in the property parameter, the properties whose data the response holds (instead of property) |  [optional] |
|**excludedProperties** | [**List&lt;SearchConsoleExcludedProperty&gt;**](SearchConsoleExcludedProperty.md) | With a list or all, selected properties left out because another selected property already counts them |  [optional] |
|**propertyErrors** | [**List&lt;SearchConsolePropertyError&gt;**](SearchConsolePropertyError.md) | With a list or all, selected properties Google refused, left out of the figures |  [optional] |
|**from** | **LocalDate** |  |  [optional] |
|**to** | **LocalDate** |  |  [optional] |
|**dataThrough** | **LocalDate** | Latest date Google has published for the property, or for every combined property (it lags 2-3 days). Later days are missing, not zero. |  [optional] |
|**minImpressions** | **Integer** |  |  [optional] |
|**unmatchedOnly** | **Boolean** |  |  [optional] |
|**matchedCount** | **Integer** | Queries with at least min_impressions that match a prompt of the project, counted before unmatched_only leaves them out |  [optional] |
|**page** | **Integer** |  |  [optional] |
|**perPage** | **Integer** |  |  [optional] |
|**total** | **Integer** | Rows in the report before paging |  [optional] |
|**truncated** | **Boolean** | Present (true) when Google returned its 25,000-row maximum for a property, so the report covers its top rows only |  [optional] |
|**data** | [**List&lt;SearchConsoleAiVisibilityGapsResponseDataInner&gt;**](SearchConsoleAiVisibilityGapsResponseDataInner.md) |  |  [optional] |
|**requestId** | **String** |  |  [optional] |



